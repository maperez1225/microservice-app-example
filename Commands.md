docker network create distribuidos;

docker run -d --rm --network distribuidos --name zipkin -p 9411:9411 openzipkin/zipkin;

docker run -d --rm --network distribuidos --name auth-api -p 8000:8000 maperez1225/microservice-example-auth:0.0.1;

docker run -d --rm --network distribuidos --name users-api -p 8083:8083 maperez1225/microservice-example-users:0.0.1;

docker run -d --rm --network distribuidos --name redis -p 6379:6379 redis:7.0-alpine;

docker run -d --rm --network distribuidos --name log-message-processor -p 8050:8050 maperez1225/microservice-example-logs:0.0.1;

docker run -d --rm --network distribuidos --name todos-api -p 8082:8082 maperez1225/microservice-example-todos:0.0.1;

docker run -d --rm --network distribuidos --name frontend -p 8080:8080 maperez1225/microservice-example-front:0.0.1;