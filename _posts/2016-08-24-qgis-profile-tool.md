---
title: QGIS Profile Tool
category: Tutoriais
---
Uma ferramenta básica em Análise de Terreno é a construção de Perfis Topográficos.

No QGIS, isso pode ser feito com o Complemento ***Profile Tool*** de maneira muito simples.

![Profile](https://github.com/geosaber/r4geo/raw/gh-pages/img/Profile.png)

Você só precisa ter um Modelo Digital de Terreno (DEM) e então traçar uma linha sobre ele para o Profile Tool gerar o perfil A-A'.

Se você tiver uma Camada Vetorial do tipo Linha, é só mudar a opção ***Selection*** de ***Temporary Polyline*** para ***Selected Polyline*** (o cursor vira uma "mão" e permite selecionar a linha que se quer usar como base para traçar o perfil, como o curso de um Rio).

Depois é só salvar em PDF ou como imagem (PNG, JPG, etc). Em Table, é possível salvar os pontos ao longo do perfil (com coordenadas).

Em *Settings* pode-se escolher entre as bibliotecas de gráficos ***Matplotlib*** ou ***Qwt5*** para gerar o gráfico do perfil.
