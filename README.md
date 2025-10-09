# clarity-demo

This is a demo app for learning testing MS Azure, Fast API and Next.js for a RAG application.

Learning/Build Plan:
1. Docker: Containerise Front end and Back end. <br/>
Azure proved expensive for casual testing, Docker provides a development platform which can be ported easily from AWS (used for testing) and Azure (where final deployment is likely to occur)
2. Next.js Front End: Build out basic webpage containing
3. Fast API Back End: Connect Fast API through to Gemini and create an API which enables general querying
4. Deploy to AWS: Verify function on AWS
5. Temporary Deploy to AZURE: Confirm that current development is portable to Azure
6. Establish Cost of AZURE Database Deployment: Check the cost of deploying our database to Azure AI Foundary
7. OPT A: IF COST IS LOW: Direct implement using AZURE Search, connected to a Data Lake or Blob Storage<br/>
   OPT B: IF COST IS HIGH:
     - Implement a FAST API API which implements current RAG logic (this should continue to be portable)
     - Vectorise data such that the correct entries can be retrieved and store data on SQL database -> swap for AZURE equivalents

# Dependencies (Local)
1. Install Docker Desktop. Follow instructions on the [Docker Website](https://www.docker.com/products/docker-desktop/).
2. Launch Docker containers for the Front End ~and Back End~
