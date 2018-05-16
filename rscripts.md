# R Scripts e Webapps

Para maiores informações, visite nosso site [Geosaber](https://www.geosaber.com.br) e conheça mais sobre o Desenvolvimento de ***Shinyapps, [Rwebapps](https://www.opencpu.org/apps.html) e Rscripts {QGIS}*** e também sobre ***Cursos de R e QGIS***.

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
