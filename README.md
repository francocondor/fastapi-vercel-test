# FastAPI deploy with Vercel

This is a guide on how to deploy a FastAPI application using Vercel.

## Prerequisites

Before getting started, make sure you have the following:

- Python installed on your machine
- Vercel account (sign up at https://vercel.com)

## Steps

1. Create a new directory "api" for your "main.py"
2. Write your FastAPI Code in "main.py"

```powershell
from fastapi import FastAPI

app = FastAPI()


@app.get('/')
async def health_check():
    return "The health check is successful v0.0.1!"
```

3. Create your requeriments.txt
```powershell
fastapi
uvicorn
```

4. Config a vercel.json
```powershell
{
  "builds": [
    {
      "src": "api/main.py",
      "use": "@vercel/python"
    }
  ],
  "routes": [
    {
      "src": "/(.*)",
      "dest": "api/main.py"
    }
  ]
}
```
5. Open terminal to start vercel 