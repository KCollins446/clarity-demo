(From /fast_api Directory)

Create environment:
```bash
python3 -m venv .venv
source .venv/bin/activate

pip install "requirements.txt"
```

Requirements should consist of bare minimum packages:
- fastapi[standard]
- uvicorn[standard]


To Update requirements:
```bash
pip freeze > requirements.txt
```


To build Docker Container
```bash
docker build -t clarity-backend:latest .
```

To run Docker Container 
```bash 
docker run -p 8000:8000 clarity-backend
```