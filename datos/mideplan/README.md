# Regiones socioeconómicas

## Geometrías simplificadas

Código en R:

```r
library(dplyr)
library(sf)

# Regiones socioeconómicas
st_read(
  dsn = "datos/mideplan/regiones-socioeconomicas-simplificadas_100m.geojson",
  quiet = TRUE
) |>
st_transform(5367) |>
st_simplify(dTolerance = 10, preserveTopology = TRUE) |>
st_write("datos/mideplan/regiones_socioeconomicas_simp_10m_temp.geojson")
```

El campo de código se agregó con QGIS.
