---
title: Cursos de QGIS e R
feature_text: |
  # Geosaber
  10 anos ministrando Cursos de SIG livres, presenciais on site e in company
feature_image: "https://unsplash.it/1300/400?image=971"
excerpt: "Iniciado em 2007, o grupo [Geosaber](http://www.geosaber.com.br) foi criado com o intuito de ser referência em Sistemas de Informações Geográficas Livres e Abertas, em especial nas geotecnologias suportadas pela [Fundação OSGeo](http://www.osgeo.org) como o ***QGIS*** e ***GRASS GIS***."
---

Fomos os primeiros a ofertar **Cursos de QGIS** no Brasil e somos os únicos a oferecer um **Curso de QGIS e R para Geoestatística** com rotinas funcionais - *Rscripts* - completas e integradas para ***Calculo e Modelagem de Variograma e Estimativas por Krigagem Ordinária e Universal*** desenvolvidas por Nós e que estão sendo utilizadas pelos alunos que passaram por nosso Curso.

{% include button.html text="Github" icon="github" link="https://github.com/geosaber" color="#0366d6" %} {% include button.html text="Geosaber" link="http://www.geosaber.com.br" color="#F4A460" %} {% include button.html text="Compartilhe" icon="facebook" link="https://www.facebook.com/Sidney.Geosaber" color="#1DA1F2" %} {% include button.html text="Shinyapps" link="https://geostatistics.shinyapps.io/geoestistics_v2" color="#00FFFF" %}

# R Scripts e Webapps

Para maiores informações, visite nosso site [Geosaber](http://www.geosaber.com.br) e conheça mais sobre o Desenvolvimento de ***Shinyapps, [Rwebapps](https://www.opencpu.org/apps.html) e Rscripts {QGIS}*** e também sobre ***Cursos de R e QGIS***.

## Rscripts (QGIS)

#### Conjunto de rotinas do R para executar comandos dentro do QGIS de forma integrada.

**QGIS** é um software livre de *Sistemas de Informação Geográfica (SIG)* que permite usar de forma integrada a *Linguagem Computacional Estatística* **R** adicionando um conjunto de diversas ferramentas que auxiliam nas análises de dados espaciais entre elas o uso de pacotes Geoestatísticos e não Geoestatísticos. Estas ferramentas são incorporadas por meio de *Rscripts* (***Caixa de Ferramentas de Processamento do QGIS***) executando comandos dentro do QGIS.

```markdown
##Basic statistics=group
##Layer=vector
##Field=Field Layer
Summary_statistics<-data.frame(rbind(sum(Layer[[Field]]),
length(Layer[[Field]]),
length(unique(Layer[[Field]])),
min(Layer[[Field]]),
max(Layer[[Field]]),
max(Layer[[Field]])-min(Layer[[Field]]),
mean(Layer[[Field]]),
median(Layer[[Field]]),
sd(Layer[[Field]])),row.names=c("Sum:","Count:","Unique values:","Minimum value:","Maximum value:","Range:","Mean value:","Median value:","Standard deviation:"))
colnames(Summary_statistics)<-c(Field)
>Summary_statistics
```

## Plataforma Web de Aplicações do R
Aplicações [Shinyapps](https://geostatistics.shinyapps.io/geoestistics_v2) para Geoestatistica e Analise de Dados Espaciais online.

![Geoestatística 3D](/img/Geoestat3D.png)

### Licença

***Copyright 2018 Geosaber***

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />Esse trabalho está licenciado sob a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.
