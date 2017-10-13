docker run -e POSTGRES_PASSWORD=Zxcv1234 -e POSTGRES_DB=survey -v `pwd`/database:/var/lib/postgresql/data -p 5432:5432 -d postgres

mkdir api \
cd api \
feathers generate app
feathers generate authentication