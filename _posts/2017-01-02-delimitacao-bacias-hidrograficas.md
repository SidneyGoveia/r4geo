---
title: QGIS 2 - Delimitação de Bacias Hidrográficas
category: Tutoriais
feature_image: "https://picsum.photos/5032/2920?image=976"
tag: bacias hidrográficas, QGIS, GRASS GIS
---
## Delimitação de Bacias Hidrográficas e Extração de Redes de Drenagens

Usando os módulos do **GRASS** pelo menu Processamento no **QGIS** é possível fazer a *<span class="underline">delimitação das bacias
hidrográficas</span>* e *<span class="underline">extração da rede de drenagens</span>* (***r.watershed***) de forma quase automatizada.
Inclusive delimitar um bacia em particular, entrando as coordenadas do ponto de <span class="underline">*exutório*</span> (***r.water.outlet***).

![Bacias_GRASS7](https://github.com/geosaber/r4geo/raw/gh-pages/img/Bacias_GRASS7.png)

### Passo a Passo

Primeiro baixe o Modelo Digital de Elevação (DEM) no serviço [EarthExplorer.USGS.gov](http://earthexplorer.usgs.gov/):
{*Data Sets >Digital Elevation > SRTM > SRTM 1 Arc-Second Global*}
São os dados originais da Missão de Topografia por RADAR da Endeavour (de 30 por 30 metros).
Dois passos iniciais são importantes:

1.  Fazer o Mosaico {*Raster > Miscelânea > Mosaico*} caso precise de mais de uma cena para cobertura;
2.  Converter o Sistema de Referência Espacial para WGS 84 / UTM 22S {botão direito na *Camada > Salvar Como...*}.

A cena escolhida para este Tutorial foi a *SRTM1S23W050V3* (GeoTIFF 1 Arc-second 24.8 MB) que recobre a cidade de Bauru - SP.

Em nossa apostila Mapas Temáticos no QGIS e outras postagens aqui no Blog já ensinamos a importar a paleta [CpT-City](http://soliton.vm.bytemark.co.uk/pub/cpt-city/index.html) com os gradientes de cores para Topografia e fazer um Relevo Sombreado
{Raster \> Análise de Terreno \> Relevo Sombreado} para usar de fundo e dar a textura tridimensional.

## *GRASS 7 Watershed Delineation*

Primeiro vamos utilizar o **módulo *<span class="underline">r.watershed</span>*** para Delimitar as Bacias Hidrográficas e Extrair a Rede de Drenagem {*Processamento \> Caixa de Ferramentas \> Comandos GRASS GIS 7 \> Raster \> r.watershed*}

![r.watershed](https://github.com/geosaber/r4geo/raw/gh-pages/img/r.watershed.png)

Apenas um parâmetro é essencial: *Minimum size of exterior watershed basin* (quantidade de células para formar uma Bacia). E marque para
gerar os três produtos:

1.  *Drainage direction* (direção de escoamento - vertentes);
2.  *Unique label for each watershed basin* (as bacias hidrográficas);
3.  *Stream segments* (rede de drenagem).

![Bacias_Drenagens](https://github.com/geosaber/r4geo/raw/gh-pages/img/Bacias_Drenagens.png)

As Drenagens e as Bacias são Raster, então para convertê-las para Vetor vamos usar o módulo ***r.to.vect***
{*Processamento \> Caixa de Ferramentas \> Comandos GRASS GIS 7 \> Raster \> r.to.vect*}

![r2vector](https://github.com/geosaber/r4geo/raw/gh-pages/img/r2vect.png)

### Delimitação de Bacia usando um [exutório](http://www.dicionario.pro.br/index.php/Exut%C3%B3rio)

No passo anterior, geramos um mapa de orientação das vertentes (direção de escoamento) - *Drainage direction*. Vamos usar esse Raster para gerar uma Bacia que selecionamos entrando as Coordenadas do Ponto de Exutório dessa Bacia. Observação: para usar o módulo
*<span class="underline">**r.water.outlet**</span>* as Coordenadas devem ser exatamente da célula (pixel) que constitui o exutório da bacia. Você pode clicar no botão à direita da caixa de coordenadas do exutório que ele alterna para a tela do QGIS. Dessa forma, se pode clicar no MDE no ponto de exutório e ele captura as coordenadas automaticamente.
{*Processamento \> Caixa de Ferramentas \> Comandos GRASS 7 \> Raster \> r.water.outlet*}

![r.water.outlet](https://github.com/geosaber/r4geo/raw/gh-pages/img/r.water.outlet_GRASS7.png)

Os resultados ainda podem ser melhorados usando outros módulos do GRASS 7:

  - ***r.shaded.relief*** - Relevo Sombreado
  - ***v.generalize*** - suavização das linhas de drenagem (use o método *chaiken*)

![v.generalize](https://github.com/geosaber/r4geo/raw/gh-pages/img/v.generalize.png)

O resultado final pode ser conferido abaixo:

![bacias_exutorio](https://github.com/geosaber/r4geo/raw/gh-pages/img/bacias_exutorio.png)

### Referências:

- [Watershed analysis](http://www.ing.unitn.it/~grass/docs/tutorial_641_en/htdocs/esercitazione/dtm/dtm4.html)

### 

![Licença Creative Commons](https://i.creativecommons.org/l/by-nc-nd/4.0/88x31.png) Este
obra está licenciada sob a Licença [Creative Commons Atribuição-NãoComercial-SemDerivações 4.0 Internacional](http://creativecommons.org/licenses/by-nc-nd/4.0/).
