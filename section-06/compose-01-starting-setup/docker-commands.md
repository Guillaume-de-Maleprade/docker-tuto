# Create Network

```docker
docker network create goals-net
```

# Run MongoDB Container

```docker
docker run --name mongodb \
  -e MONGO_INITDB_ROOT_USERNAME=max \
  -e MONGO_INITDB_ROOT_PASSWORD=secret \
  -v data:/data/db \
  --rm \
  -d \
  --network goals-net \
  mongo
```

# Build Node API Image

```docker
docker build -t goals-node .
```

# Run Node API Container

```docker
docker run --name goals-backend \
  -e MONGODB_USERNAME=max \
  -e MONGODB_PASSWORD=secret \
  -v logs:/app/logs \
  -v /Users/maximilianschwarzmuller/development/teaching/udemy/docker-complete/backend:/app \
  -v /app/node_modules \
  --rm \
  -d \
  --network goals-net \
  -p 80:80 \
  goals-node
```

# Build React SPA Image

```docker
docker build -t goals-react .
```

# Run React SPA Container

```docker
docker run --name goals-frontend \
  -v /Users/maximilianschwarzmuller/development/teaching/udemy/docker-complete/frontend/src:/app/src \
  --rm \
  -d \
  -p 3000:3000 \
  -it \
  goals-react
```

# Stop all Containers

```docker
docker stop mongodb goals-backend goals-frontend
```
