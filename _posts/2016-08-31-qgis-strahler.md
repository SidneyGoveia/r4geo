---
title: QGIS Strahler Plugin
category: Tutoriais
feature_image: "https://picsum.photos/200/300/?random"
---
<span style="font-family: Arial , Helvetica , sans-serif;">Esse
Complemento calcula o número ***Strahler*** (ordem/hierarquia) de cada
segmento em uma rede de drenagem e adiciona ele em um novo Campo na
Tabela de Atributos.</span>

<table>
<tbody>
<tr class="odd">
<td style="text-align: center;"><a href="https://4.bp.blogspot.com/-sQW5N-VYT8c/WBe4rqZDCcI/AAAAAAAACJM/4XV9bTz8ISUIQoa9RKYUH61NBWiLiOQzACEw/s1600/Strahler_Table.png"><img src="https://4.bp.blogspot.com/-sQW5N-VYT8c/WBe4rqZDCcI/AAAAAAAACJM/4XV9bTz8ISUIQoa9RKYUH61NBWiLiOQzACEw/s1600/Strahler_Table.png" /></a></td>
</tr>
<tr class="even">
<td style="text-align: center;"><span style="font-family: Arial , Helvetica , sans-serif; font-size: small;"><a href="https://github.com/ArMoraer/QGISStrahler" class="uri">https://github.com/ArMoraer/QGISStrahler</a></span></td>
</tr>
</tbody>
</table>

<span style="font-family: Arial , Helvetica , sans-serif;">Primeiro,
selecione o segmento que representa a raiz da rede (**exutório**). Este
segmento deve ser ligado ao resto da rede por apenas um ponto de
extremidade.</span>

<span style="font-family: Arial , Helvetica , sans-serif;">Somente um
segmento pode ser selecionado. Clique no ícone do plugin: será
solicitado o nome do atributo novo (o padrão é ***strahler***). Se um
campo com esse nome já existe, uma janela de confirmação perguntará se
você deseja substituí-lo.</span>

<table>
<tbody>
<tr class="odd">
<td style="text-align: center;"><a href="https://3.bp.blogspot.com/-C4ZBLvMa0JQ/WBe6CTlrGiI/AAAAAAAACJU/vtIF4nnpwyUYJ-pq69XTCatZvvJz1PanwCLcB/s1600/Strahler.png"><img src="https://3.bp.blogspot.com/-C4ZBLvMa0JQ/WBe6CTlrGiI/AAAAAAAACJU/vtIF4nnpwyUYJ-pq69XTCatZvvJz1PanwCLcB/s1600/Strahler.png" /></a></td>
</tr>
<tr class="even">
<td style="text-align: center;"><span style="font-family: Arial , Helvetica , sans-serif; font-size: small;"><a href="https://github.com/ArMoraer/QGISStrahler" class="uri">https://github.com/ArMoraer/QGISStrahler</a></span></td>
</tr>
</tbody>
</table>

<span style="font-family: Arial , Helvetica , sans-serif;">Outros
Complementos podem ser usados em conjunto, como o ***[Stream Feature
Extractor]*** - u</span><span
style="font-family: Arial , Helvetica , sans-serif;">m plugin do QGIS
para extrair características de fluxo (nascentes, sumidouros,
confluências, etc) de uma rede de fluxo.</span>

<span style="font-family: Arial , H
"></span>

  [Stream Feature Extractor]: https://github.com/kartoza/stream_feature_extractor
  
<span style="font-family: Arial , Helvetica , sans-serif;">E também tem
o Complemento ***Generalizer*** (que é parcialmente baseado no
módulo </span><span
style="font-family: Arial , Helvetica , sans-serif;">***v.generalize***
do **GRASS**) para simplificar (reduzir vértices) e suavizar
(arredondar) as linhas de drenagem.</span>

[![][1]][1]

#### <span style="font-family: Arial , Helvetica , sans-serif;">Referência:</span>

-   <https://en.m.wikipedia.org/wiki/Strahler_number>

  [1]: https://4.bp.blogspot.com/-wB8gyzXK-Pg/WBe9SEI3yeI/AAAAAAAACJo/OYPj5csUM10KmmuQNbV7zkVGz5W7T9RRwCLcB/s1600/Generalizer.png
