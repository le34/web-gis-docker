docker run -e POSTGRES_PASSWORD=Zxcv1234 -e POSTGRES_DB=survey -v `pwd`/database:/var/lib/postgresql/data -p 5432:5432 -d mdillon/postgis:9.6

mkdir api \
cd api \
feathers generate app
feathers generate authentication

# web-gis-feathers
docker build -t web-gis-feathers .
docker tag web-gis-feathers runetvilum/web-gis-feathers
docker push runetvilum/web-gis-feathers
# web-gis-app
docker build -t web-gis-app .
docker tag web-gis-app runetvilum/web-gis-app
docker push runetvilum/web-gis-app
# Compose
docker stack deploy -c docker-compose.yml survey