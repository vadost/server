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
docker build -t vadost/postgres .
docker login -u="vadost" -p="password";
docker push vadost/postgres

## SSH
alias awix='ssh vadost@46.101.237.67'
alias awixfs='sshfs vadost@46.101.237.67:~ ~/SERVER_MOUNT'
alias awixfsu='fusermount -u ~/SERVER_MOUNT'
