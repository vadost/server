## SERVER START
POSTGRES_USER=postgres POSTGRES_PASSWORD=postgres docker-compose up -d

## POSTGRES BUILD
docker build -t misticwonder/postgres .
docker login -u="misticwonder" -p="password";
docker push misticwonder/postgres
