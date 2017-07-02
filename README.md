## SERVER START
CADDY_FILE=caddylocal \
POSTGRES_USER=postgres \
POSTGRES_PASSWORD=postgres \
POSTGRES_HOST=postgres \
SECRET=secret \
docker-compose up -d

## POSTGRES BUILD
docker build -t misticwonder/postgres .
docker login -u="misticwonder" -p="password";
docker push misticwonder/postgres
