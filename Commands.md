docker network create distribuidos;

docker run -d --rm --network distribuidos --name zipkin -p 9411:9411 openzipkin/zipkin;

docker run -d --rm --network distribuidos --name auth-api -p 8000:8000 maperez1225/auth-api:0.0.1;

docker run -d --rm --network distribuidos --name users-api -p 8083:8083 maperez1225/users-api:0.0.1;

docker run -d --rm --network distribuidos --name redis -p 6379:6379 redis:7.0-alpine;

docker run -d --rm --network distribuidos --name log-message-processor maperez1225/log-message-processor:0.0.1;

docker run -d --rm --network distribuidos --name todos-api -p 8082:8082 maperez1225/todos-api:0.0.1;

docker run -d --rm --network distribuidos --name frontend -p 8080:8080 maperez1225/microservice-app-example-frontend:0.0.1;