# A simple MERN stack application

## Create a network for the docker containers

```
docker network create demo
```

## Build the client
```
cd mern/frontend
docker build -t mern-frontend .
```

## Run the client

```
docker run --name=frontend --network=demo -d -p 5173:5173 mern-frontend
```

## Verify the client is running

Open your browser and type `http://localhost:5173`

## Run the mongodb container

```
docker run --network=demo --name mongodb -d -p 27017:27017 -v ~/opt/data:/data/db mongo:latest
```

## Build the server

```
cd mern/backend
docker build -t mern-backend
```

## Run the server

```
docker run --name=backend --network=demo -d -p 5050:5050 mern-backend
```

## Using Docker Compose

```
docker compose up -d
```

<img width="1790" alt="Screenshot 2024-08-31 at 11 07 58 PM" src="https://github.com/user-attachments/assets/f414230b-8bd6-4393-b8de-6a10444a8dfd">
