# Registros de presencia agrupados por GBIF

## Remoción de registros sin identificación en el nivel de especie

Código en R:

```r
library(tidyr)
library(readr)
library(dplyr)

# Mamíferos
# https://www.gbif.org/occurrence/download/0031158-230530130749713
read_delim(
  file = "datos/gbif/mamiferos-raw.csv",
  col_select = c(
    "gbifID", "occurrenceID", "institutionCode", "collectionCode",
    "kingdom", "phylum", "class", "order", "family", "genus", "species",
    "locality", "decimalLatitude", "decimalLongitude",
    "eventDate", "day", "month", "year"
  )
) |>
drop_na(species) |>
write_delim("datos/gbif/mamiferos.csv", delim = "\t", na = "")

# Orquídeas
# https://www.gbif.org/occurrence/download/0031171-230530130749713
read_delim(
  file = "datos/gbif/orquideas-raw.csv",
  col_select = c(
    "gbifID", "occurrenceID", "institutionCode", "collectionCode",
    "kingdom", "phylum", "class", "order", "family", "genus", "species",
    "locality", "decimalLatitude", "decimalLongitude",
    "eventDate", "day", "month", "year"
  )
) |>
drop_na(species) |>
write_delim("datos/gbif/orquideas.csv", delim = "\t", na = "")

# Vipéridos
# https://www.gbif.org/occurrence/download/0020196-230530130749713
read_delim("datos/gbif/viperidos-raw.csv") |>
drop_na(species) |>
write_delim("datos/gbif/viperidos.csv", delim = "\t", na = "")
```
