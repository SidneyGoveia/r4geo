---
title: QGIS 3 - Delimitação de Bacias Hidrográficas
category: General
feature_image: "https://picsum.photos/5032/2920?image=976"
tag: bacias hidrográficas, QGIS 3
---
# Delimitação Automática de Bacias Hidrográficas no QGIS 3.0
Para fazer a Extração de Rede de Drenagens e Delimitação de Bacias Hidrográficas no QGIS 3.0 vamos usar o GRASS 7.4:
> ***Processar - Caixa de Ferramentas -> GRASS -> Raster***

## Modelo Digital de Elevação
Para esse tutorial, vamos usar o MDE (Modelo Digital de Elevação) de resolução de 12.5 metros do PALSAR (interferometria por RADAR) do satélite japonês ALOS.
- ***Alaska Satellite Facility (ASF) -> Datasets -> SAR Datasets -> ALOS PALSAR***
![ASF](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_PALSAR_ASF.png)

- **Características da cena escolhida**
![Granule](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_PALSAR.png)

- **Estilo de Relevo Sombreado no QGIS**
![Estilo](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_Estilo.png)

- **Relevo Sombreado no QGIS**
![Hillshade](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_Hillshade.png)

## Análise Hidrológica no QGIS

### Extração de Rede de Drenagens
> *r.stream.extract*

![Extract](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_r_stream.extract.png)

- **Rede de Drenagens**
![Streams](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_unique_stream.png)

### Delimitação de Bacias Hidrográficas
> *r.watershed*

![Watershed](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_r_watershed.png)

- **Bacias Hidrográficas**
![Watershed Basin](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_watershed_basin.png)

### Conversão Raster > Vetor (Polígonos)
> *r.to.vect*

![Vector](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_r_to_vect_watershed_basin.png)

### Delimitação de Bacia a partir de um Exutório
> *r.water.outlet*

![Outlet](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_r_water_outlet.png)

### Conversão Raster > Vetor (Polígonos)
> *r.to.vect*

![Vector](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_r_to_vect_basin.png)

- **Bacia delimitada a partir de exutório**
![Bacias](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_basin_outlet.png)