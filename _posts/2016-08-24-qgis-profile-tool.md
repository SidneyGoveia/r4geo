---
title: QGIS Profile Tool
category: General
feature_image: "https://picsum.photos/200/300/?random"
---
<span style="font-family: Arial , Helvetica , sans-serif;">Um ferramenta básica em Análise de Terreno é a construção de Perfis Topográficos.</span>

<span style="font-family: Arial , Helvetica , sans-serif;">No QGIS, isso pode ser feito com o Complemento ***Profile Tool*** de maneira muito simples.</span>

<div class="separator" style="clear: both; text-align: center;">

![](https://github.com/geosaber/r4geo/raw/gh-pages/img/Profile.png)

</div>

<span style="font-family: Arial , Helvetica , sans-serif;">Você só precisa ter um Modelo Digital de Terreno (DEM) e então traçar uma linha
sobre ele para o Profile Tool gerar o perfil A-A'.</span>

<span style="font-family: Arial , Helvetica , sans-serif;">Se você tiver uma Camada Vetorial do tipo Linha, é só mudar a opção ***Selection*** de ***Temporary Polyline*** para ***Selected Polyline*** (o cursor vira uma "mão" e permite selecionar a linha que se quer usar como base para traçar o perfil, como o curso de um Rio).</span>

<span style="font-family: Arial , Helvetica , sans-serif;">Depois é só salvar em PDF ou como imagem (PNG, JPG, etc). Em Table, é possível
salvar os pontos ao longo do perfil (com coordenadas).</span>

<span style="font-family: Arial , Helvetica , sans-serif;">E em Settings pode-se escolher entre as bibliotecas de gráficos Matplotlib ou Qwt5 para gerar o gráfico do perfil.</span>

<div class="separator" style="clear: both; text-align: center;">

</div>
