---
title: QGIS 3.0 ArcGISMapServer Imagery
category: General
feature_image: "https://picsum.photos/200/300/?random"
---
# Provedores de Dados no QGIS 3.0
A primeira das dúvidas que surgiu com o lançamento do **QGIS 3.0** foi como inserir Imagens e Mapas de fundo, uma vez que o Complemento *QuickMapServices* (substituto do *OpenLayers Plugin*, que é obsoleto).
A resposta está em uma solução antiga, que publicamos em nosso blog: [Alternativa ao OpenLayers no QGIS](https://sites.google.com/site/geosaber/Tutoriais/alternativaaoopenlayersnoqgis) mas que agora está muito mais fácil de se aplicar.

## ARCGIS REST API SERVICE no QGIS
Entre no *Data Source Manager* {Camadas > Gerenciador de Fontes de Dados} e escolha ***Servidor de Mapas do ArcGIS***

![ArcGIS MapServer](https://github.com/geosaber/r4geo/raw/gh-pages/img/ArcGISREST02.png "Data Source Manager")

Em *Conexões de servidor* clique em *Novo* e insira a URL do [World Imagery](http://server.arcgisonline.com/arcgis/rest/services/World_Imagery/MapServer)

![World Imagery](https://github.com/geosaber/r4geo/raw/gh-pages/img/ArcGISREST01.png "World Imagery")

Escolha a Imagem e clique em Adicionar para acrescentar à lista de Camadas. Na aba do *Navegador* vai aparecer a conexão *ArcGISMapServer* onde se pode acrescentar outras Imagens, disponíveis no *World Imagery*.

![QGIS 3 ArcGIS REST API](https://github.com/geosaber/r4geo/raw/gh-pages/img/ArcGISREST03.png "QGIS 3 ArcGIS REST API")

> Também existem outras camadas disponíveis no **Serviço de Mapas do ArcGIS**, basta alterar o nome ao inserir a URL:

### Serviços
```
- ESRI_Imagery_World_2D (MapServer)
- ESRI_StreetMap_World_2D (MapServer)
- I3_Imagery_Prime_World (GlobeServer)
- NASA_CloudCover_World (GlobeServer)
- NatGeo_World_Map (MapServer)
- NGS_Topo_US_2D (MapServer)
- Ocean_Basemap (MapServer)
- USA_Topo_Maps (MapServer)
- World_Imagery (MapServer)
- World_Physical_Map (MapServer)
- World_Shaded_Relief (MapServer)
- World_Street_Map (MapServer)
- World_Terrain_Base (MapServer)
- World_Topo_Map (MapServer)
```
---
### Referências
* [HOW TO USE ARCGIS REST API SERVICE IN QGIS](http://www.geodose.com/2017/08/how-to-use-arcgis-rest-api-service-qgis.html)
* [ArcGIS Map Server](http://server.arcgisonline.com/arcgis/rest/services)
