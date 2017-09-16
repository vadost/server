## SERVER START
NODE_ENV=development \
CADDY_FILE=caddylocal \
POSTGRES_USER=postgres \
POSTGRES_PASSWORD=postgres \
docker-compose up -d

or create .env file with
  NODE_ENV=production
  CADDY_FILE=caddyserver
  POSTGRES_USER=postgres
  POSTGRES_PASSWORD=postgres
and run docker-compose up -d

## POSTGRES BUILD
docker build -t misticwonder/postgres .
docker login -u="misticwonder" -p="password";
docker push misticwonder/postgres

## SSH
alias clubnika='ssh misticwonder@178.62.33.39'
alias clubnikafs='sshfs misticwonder@178.62.33.39:~ ~/SERVER_MOUNT'
alias clubnikafsu='fusermount -u ~/SERVER_MOUNT'
