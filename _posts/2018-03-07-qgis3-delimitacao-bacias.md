---
title: Delimitação de Bacias Hidrográficas
category: General
feature_image: "https://picsum.photos/200/300/?random"
tag: bacias hidrográficas, QGIS 3
---
# Delimitação Automática de Bacias Hidrográficas no QGIS 3.0

## MDE ALOS PALSAR
Para esse tutorial, vamos usar o MDE (Modelo Digital de Elevação) de resolução de 12.5 metros do PALSAR (interferometria por RADAR) do satélite japonês ALOS.
![ASF](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_PALSAR_ASF.png)

### Características da cena escolhida
![Granule](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_PALSAR.png)

### Estilo de Relevo Sombreado no QGIS
![Estilo](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_Estilo.png)

### Relevo Sombreado no QGIS
![Hillshade](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_Hillshade.png)

## Extração de Rede de Drenagens
![Extract](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_r_stream.extract.png)

### Rede de Drenagens
![Streams](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_unique_stream.png)

## Delimitação de Bacias Hidrográficas
![Watershed](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_r_watershed.png)

### Bacias Hidrográficas
![Watershed Basin](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_watershed_basin.png)

### Conversão Raster > Vetor (Polígonos)
![Vector](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_r_to_vect_watershed_basin.png)

## Delimitação de Bacia a partir de um Exutório
![Outlet](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_r_water_outlet.png)

### Conversão Raster > Vetor (Polígonos)
![Vector](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_r_to_vect_basin.png)

### Bacia delimitada a partir de exutório
![Bacias](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_basin_outlet.png)
