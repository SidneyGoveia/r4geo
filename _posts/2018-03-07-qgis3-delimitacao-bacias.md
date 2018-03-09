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
Para esse tutorial, vamos usar o MDE (Modelo Digital de Elevação) de resolução de 12.5 metros do PALSAR (interferometria por RADAR) do satélite japonês ALOS. Ele já vem em Sistema de Referência Espacial UTM.

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

**OBS:** quanto **maior** o valor usado em *Minimum flow accumulation for streams* mais detalhada será a Rede de Drenagens, ou seja, uma resolução maior é usada. {use 10 como valor inicial}

- **Rede de Drenagens**
![Streams](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_unique_stream.png)

- Para melhorar as linhas da drenagem (suavizar) você pode generalizá-las
> ***Vector*** -> *v.generalize*  

### Delimitação de Bacias Hidrográficas
> *r.watershed*

![Watershed](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_r_watershed.png)

**OBS:** quanto **menor** o valor usado em *Minimum size of exterior watershed basin* mais subbacias serão geradas, ou seja, menos células para definir uma bacia. {use 10000 como valor inicial}

Três saídas são importantes:
- *Drainage direction* - Usado para fazer a Delimitação de uma bacia a partir de um exutório {'ponto de fuga'};
- *Unique label for each watershed basin* - as Bacias Hidrográficas {'raster colorido'}
- *Stream segments* - Rede de Drenagem (se você não tiver extraído no passo anterior); {'raster'}

- **Bacias Hidrográficas**
![Watershed Basin](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_watershed_basin.png)

### Conversão Raster > Vetor (Polígonos)
> *r.to.vect*

![Vector](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_r_to_vect_watershed_basin.png)

### Delimitação de Bacia a partir de um Exutório
> *r.water.outlet*

![Outlet](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_r_water_outlet.png)

**OBS:** cuidado ao marcar o ponto de exutório. {use somente números inteiros com X,Y separados por vírgula}

### Conversão Raster > Vetor (Polígonos)
> *r.to.vect*

![Vector](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_r_to_vect_basin.png)

- **Bacia delimitada a partir de exutório**
![Bacias](https://github.com/geosaber/r4geo/raw/gh-pages/img/ALOS_basin_outlet.png)
