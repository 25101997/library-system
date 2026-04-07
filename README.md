git init
git branch -M main
git remote add origin https://github.com/25101997/library-system.git
git add .
git commit -m "first commit"
git push -u origin main

git branch

git checkout -b dev
git push -u origin dev

git checkout dev
git pull origin dev
git add .
git commit -m "Added new edits"
git push origin dev

git checkout main
git pull origin main
git merge dev
git push origin main

cp .env.example .env

docker build -t library-api ./apps/api
docker build -t library-web ./apps/web

docker rmi library-system-api
docker rmi library-system-web

apps/api$ docker run -it --rm -v "$PWD":/api -u $(id -u):$(id -g) -w /api -e DOTNET_CLI_HOME=/api -p 8080:8080 mcr.microsoft.com/dotnet/sdk:8.0 sh

dotnet new webapi --output .

apps$ docker run -it --rm -v "$PWD":/apps -u $(id -u):$(id -g) -w /apps -p 4200:4200 node:18-alpine sh

npx @angular/cli@16.2.0 new web --routing --style=css

docker rm -f library-system-db
docker rm -f library-system-api
docker rm -f library-system-web

docker compose -f docker-compose.dev.yml up