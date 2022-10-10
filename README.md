# docker OpenStreetMap Local

```bash

docker run -it \
  -e PBF_URL=http://download.geofabrik.de/europe/italy/nord-ovest-latest.osm.pbf \
  -e REPLICATION_URL=https://download.geofabrik.de/europe/italy-updates \
  -p 8082:8080 \
  --name nominatim-italy \
  mediagis/nominatim:4.1
```

```bash

docker run \
  -e OVERPASS_META=yes \
  -e OVERPASS_MODE=init \
  -e OVERPASS_PLANET_URL=http://download.geofabrik.de/europe/italy/nord-ovest-latest.osm.bz2 \
  -e OVERPASS_DIFF_URL=http://download.openstreetmap.fr/replication/europe/italy/minute/ \
  -e OVERPASS_RULES_LOAD=10 \
  -v /big/docker/overpass_db/:/db \
  -p 12345:80 \
  -i -t \
  --name overpass_monaco wiktorn/overpass-api

```