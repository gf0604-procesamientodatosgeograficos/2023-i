# Apuntes técnicos

## Ambiente Conda

### Creación

``` shell
# Creación de ambiente Conda
conda update conda -y
conda create -y -n gf0604-2023-i
conda activate gf0604-2023-i
conda config --env --add channels conda-forge
conda config --env --set channel_priority strict
conda install -y mamba
mamba install -y r-base r-essentials \
                 r-vroom=1.5.7 \
                 r-xaringan \
                 r-dplyr \
                 r-dt \
                 r-ggplot2 r-ggthemes r-hrbrthemes r-plotly \
                 r-sf=1.0_6 r-leaflet r-leaflet.providers r-leaflet.extras r-leaflet.minicharts r-leafem \
                 r-shiny r-shinythemes r-shinycssloaders \
                 r-rsconnect
```

### Borrado

``` shell
# Borrado de ambiente Conda
conda deactivate
conda env remove --name gf0604-2023-i
```
