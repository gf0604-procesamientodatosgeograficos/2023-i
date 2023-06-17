# Áreas de conservación, áreas silvestres protegidas

## Geometrías sin simplificar

Comandos de GDAL/OGR:

```shell
# Áreas de conservación
ogr2ogr \
  -makevalid \
  areas_conservacion.geojson \
  WFS:"http://geos1pne.sirefor.go.cr/wfs" "PNE:areas_conservacion"
    
# Áreas silvestres protegidas (ASP)
ogr2ogr \
  -makevalid \
  asp.geojson \
  WFS:"http://geos1pne.sirefor.go.cr/wfs" "PNE:areas_silvestres_protegidas"
```

## Geometrías simplificadas

Código en R:

```r
library(sf)

# Áreas de conservación
st_read(
  dsn = "datos/sinac/areas_conservacion.geojson",
  quiet = TRUE
) |>
st_simplify(dTolerance = 10, preserveTopology = TRUE) |>
st_write("datos/sinac/areas_conservacion_simp_10m.geojson")

# Áreas silvestres protegidas (ASP)
st_read(
  dsn = "datos/sinac/asp.geojson",
  quiet = TRUE
) |>
st_simplify(dTolerance = 10, preserveTopology = TRUE) |>
st_write("datos/sinac/asp_simp_10m.geojson")
```
