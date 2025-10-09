
# BUILD STAGE
FROM node:20-slim AS build

RUN corepack enable

ENV PNPM_HOME="/pnpm"
ENV PATH="$PNPM_HOME:$PATH"

WORKDIR /app

COPY pnpm-lock.yaml ./

RUN --mount=type=cache,target=/pnpm/store \
    pnpm fetch --frozen-lockfile

COPY package.json ./

RUN --mount=type=cache,target=/pnpm/store \
    pnpm install --frozen-lockfile --prod --offline

COPY . .

RUN pnpm build



# RUNTIME STAGE
FROM node:20-slim AS runtime

RUN corepack enable

RUN groupadd -g 1001 appgroup && \
    useradd -u 1001 -g appgroup -m -d /app -s /bin/false appuser

WORKDIR /app
COPY --from=build --chown=appuser:appgroup /app ./

ENV NODE_ENV=production \
    NODE_OPTIONS="--enable-source-maps"

USER appuser

# Start your app
CMD ["pnpm", "start"]

EXPOSE 3000

