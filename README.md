# docker OpenStreetMap Local

```bash

docker run -it \
  -e PBF_URL=http://download.geofabrik.de/europe/italy/nord-ovest-latest.osm.pbf \
  -e REPLICATION_URL=https://download.geofabrik.de/europe/italy-updates \
  -p 8082:8080 \
  --name nominatim-italy2 \
  mediagis/nominatim:4.1
```

