---
title: QGIS Processing R Provider Plugin
category: tutorial
feature_image: "https://github.com/geosaber/r4geo/raw/gh-pages/img/osm_bkground.png"
tags: QGIS, R, Statistics, Spatial Analysis, RSpatial, 
---
## ***Processing R Provider Plugin for QGIS 3.x***
[![QGIS/R](https://github.com/geosaber/r4geo/raw/gh-pages/img/rplugin.png)](https://github.com/north-road/qgis-processing-r)

## Exemplos
- Histograma
[![QGIS/R](https://github.com/geosaber/r4geo/raw/gh-pages/img/rhisto.png)](https://github.com/north-road/qgis-processing-r)

- ***R script***
```r
##Vector processing=group
##showplots
##Layer=vector
##Field=Field Layer
hist(Layer[[Field]],main=paste("Histogram of",Field),xlab=paste(Field))
```
- Resultado
[![QGIS/R](https://github.com/geosaber/r4geo/raw/gh-pages/img/rplots.png)](https://github.com/north-road/qgis-processing-r)

### *A Processing provider for connecting to the R statistics framework*
[![QGIS/R](https://github.com/geosaber/r4geo/raw/gh-pages/img/rprocessing.png)](https://github.com/north-road/qgis-processing-r)

### R Syntax in Processing scripts
[![QGIS/R](https://github.com/geosaber/r4geo/raw/gh-pages/img/rsyntax.png)](https://docs.qgis.org/testing/en/docs/training_manual/processing/r_syntax.html)

## Referências:
- [Processing R Provider](https://plugins.qgis.org/plugins/processing_r)
- [QGIS resources repository - A repository with scripts and models downloadable from the Processing toolbox](https://github.com/qgis/QGIS-Processing)
