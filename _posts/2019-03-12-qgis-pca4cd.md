---
title: QGIS PCA for Change Detection Analysis
category: image-classification
feature_image: "https://github.com/geosaber/r4geo/raw/gh-pages/img/osm_bkground.png"
tags: QGIS, PCA, Change Detection Analysis 
---
## ***Análise de Principais Componentes para Detecção de Alterações em Imagens***
[![PCA4CD](https://github.com/geosaber/r4geo/raw/gh-pages/img/component-analysis.png)](https://smbyc.bitbucket.io/qgisplugins/pca4cd)

O PCA4CD é um plugin QGIS para construir a camada de detecção de mudança usando o método de componentes principais. Projetado principalmente com o objetivo de:
- gerar ou carregar os componentes principais (PCA)
- e construir a camada de detecção de alterações com base nas propriedades de redução da dimensionalidade.

### Versão QGIS e Python

Este plugin só funciona na versão QGIS >= 3.4, é muito recomendado usar a versão mais recente disponível do QGIS 3 com o ambiente Python 3.7 devido às dependências e alguns problemas com a biblioteca ***Dask***.

#### Pacotes python adicionais
PCA4CD requer pacotes python adicionais para funcionar, que geralmente não são parte do Python do QGIS. Estes são:
- Python-Dask
- PyQtGraph

##### O caminho para ter isso:
- Primeira maneira (recomendado e automático) é que o plugin (quando está instalando ou atualizando) será instalado em uma pasta separada específica para PCA4CD e não influenciará qualquer instalação existente do Python.
- Em segundo lugar, instalá-lo em sua instalação Python no Sistema primeiro antes de instalar o plugin, mas depende do Sistema Operacional para trabalhar.

### Como usar
Primeiro, a janela principal é dividida por duas seções:
- Computar os componentes principais
- Carregar os componentes principais

#### As seguintes etapas são:
- Análise de detecção de alterações
- Gerar a camada de alteração por componente
- Gerar a camada de alteração de mesclagem

[![PCA4CD](https://github.com/geosaber/r4geo/raw/gh-pages/img/pca4cda.png)](https://smbyc.bitbucket.io/qgisplugins/pca4cd)

> O PCA4CD foi desenvolvido, projetado e implementado pelo Grupo de Sistema de Monitoramento Florestal e de Carbono (SMByC), operado pelo Instituto de Estudos de Hidrologia, Meteorologia e Meio Ambiente (IDEAM) - Colômbia.
> Autor e desenvolvedor: Xavier Corredor Ll.

## Referências:
- [PCA4CD](https://smbyc.bitbucket.io/qgisplugins/pca4cd)
- [GRASS - Principal Components Analysis](https://grasswiki.osgeo.org/wiki/Principal_Components_Analysis)

### Artigos:
- ***PCA‐based land‐use change detection and analysis using multitemporal and multisensor satellite data***
  - [International Journal of Remote Sensing](https://doi.org/10.1080/01431160801950162)
- ***A PCA-Based Change Detection Framework for Multidimensional Data Streams***
  - [Machine Intelligence & kNowledge Engineering - MINE](https://mine.kaust.edu.sa/Documents/papers/KDD2015.pdf)
