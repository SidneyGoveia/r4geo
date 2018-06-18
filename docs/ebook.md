## Guia de Elaboração de Mapas Temáticos no QGIS 2.8 Wien

Versão completa do Tutorial em PDF (25/08/2015): [download id="5820"]

Este é um guia rápido de como montar um Mapa Temático no QGIS usando Dados Públicos.

### 1\. Início

Esse Mapa foi criado usando o QGIS 2.8.3 Wien 64 bits - LTR (versão de longa duração) no Windows 10 Professional.
![Bauru 100mil](https://sites.google.com/site/geosaber/_/rsrc/1467172203290/Tutoriais/mapastematicosnoqgis/Bauru_100mil.png)

Primeiro algumas recomendações básicas de trabalho:

-   O nome de usuário do Windows não pode conter acentuações e evite espaços entre palavras;
-   Não use a pasta 'Desktop' no Windows, porque sobrecarrega o Sistema (tudo que está em seu desktop é carregado para a memória);
-   Não use acentuação em nomes de Pastas e evite caminhos muito longos (endereços de pastas/subpastas);
-   Organize seus arquivos numa Pasta de Trabalho (*Workspace*) e armazene Imagens multibanda em pastas (facilita para fazer empilhamento das bandas e mosaicos das cenas).

### 2\. Camada Vetorial

Primeiro vamos baixar a Carta Topográfica da Folha Bauru 1:50.000 no site do IBGE (tudo deve começar com uma boa base cartográfica).
[![IBGE](https://sites.google.com/site/geosaber/_/rsrc/1467172203291/Tutoriais/mapastematicosnoqgis/IBGE.png)](http://downloads.ibge.gov.br/downloads_geociencias.htm)

No caso de não existir o arquivo .DOC com a descrição dos dados (e principalmente o Datum da Carta), você pode baixar a Carta escaneada no site:
[SF-22-Z-B-I-4](http://biblioteca.ibge.gov.br/visualizacao/mapas/GEBIS%20-%20RJ/SF-22-Z-B-I-4.jpg)

Agora, de posse dos Vetores e das informações do Sistema de Referência Espacial (SRC) onde temos SF.22 é de UTM zona 22S e no selo da Carta encontramos o Datum Córrego Alegre referente à essa Carta. Também devemos notar que as Unidades estão em Quilômetros (Km), por isso será necessário criarmos um SRC Personalizado para poder adicionar esses Vetores no QGIS.

[![QGIS](https://sites.google.com/site/geosaber/_/rsrc/1467172203291/Tutoriais/mapastematicosnoqgis/Novo_SRC.png)](http://qgis.org/pt_BR/docs/index.html)

Adicionar Camada Vetorial (mude o tipo de arquivo para DGN - do CAD *Microstation* para poder visualizar os dados do IBGE) e você terá uma janela que pede para selecionar o tipo de geometria (acontece com todo arquivo CAD \[DXF e DGN\] ou GPX \[exportação do GPS\] porque armazenam múltiplas geometrias em um único arquivo).

[![QGIS](https://sites.google.com/site/geosaber/_/rsrc/1467172203291/Tutoriais/mapastematicosnoqgis/tipo%20geometria.png)](http://qgis.org/pt_BR/docs/index.html)

O IBGE separa os Vetores por temas: Hidrografia (rios = linhas e reservatórios = polígonos); Hipsometria (Curvas de Nível = linhas e Pontos Cotados = pontos); Sistema Viário (rodovias e ferrovias = linhas, nesse caso a distinção é feita pelo atributo na coluna Level).

Ao Adicionar, o QGIS pede o SRC e você deve usar o Novo SRC que foi criado especialmente para esses arquivos DGN (coordenadas planas cartesianas e unidades em quilômetros). Outra forma de atribuir um SRC, se a Camada já foi Adicionada é clicar com o botão direita nela e usar a opção Definir o SRC da Camada (igual ao *Define Projection* no ArcGIS...). O QGIS só reconhece / trabalha com Geometrias (Pontos, Linhas e Polígonos), não reconhecendo o tipo *Annotation* (Texto) dos CADs. Para contornar isso, ele cria Pontos onde os Textos eram ancorados e armazena o texto na Tabela de Atributos (que podem ser exibidos posteriormente como Rótulos). Infelizmente, muitos textos são trazidos de forma desmembrada por letra, o que torna inútil exportar esses Pontos para *Shapefile* (arquivo vetorial padrão [OpenGIS](http://www.opengeospatial.org/)). Para exportar as Camadas para outros Formatos (SHP, KML, DXF, etc.) ou mudar o Sistema de Referência Espacial (Transformação de Sistema de Referência Espacial) é só clicar com o botão direito do mouse em cima do nome da Camada e escolher a opção Salvar Como...

[![QGIS](https://sites.google.com/site/geosaber/_/rsrc/1467172203291/Tutoriais/mapastematicosnoqgis/Salvar%20Vetor.png)](http://qgis.org/pt_BR/docs/index.html)

### 3\. Camada Raster

#### 3.2 Modelo de Terreno (Elevação)

Vamos agora baixar um Modelo Digital de Terreno (na verdade, de Elevação, pois é oriundo do processo de interferometria por RADAR e a Superfície nem sempre representa a do nível do solo, mas de qualquer coisa que esteja como Cobertura do Solo, como as copas das árvores - Dossel). Para isso, temos o serviço *Earth Explorer* do *USGS* (Serviço Geológico Americano) onde podemos adquirir Imagens de Satélite da série Landsat (1-8), com resoluções espaciais variando de 30 metros (pixel) até 15 metros - Imagem Pancromática e Modelos Digitais de Elevação - MDE do SRTM (*Shuttle Radar Topography Mission* \- Missão de Topografia por RADAR feita pelo Ônibus Espacial *Endeavour* em 11 de fevereiro de 2000) com resolução espacial de 1 arco de segundo, o que equivale à 30 metros. Nesse guia vamos usar o MDE do SRTM para fazer o Relevo Sombreado.

![](https://sites.google.com/site/geosaber/_/rsrc/1467172203291/Tutoriais/mapastematicosnoqgis/EE1.png?height=400&width=225)

![](https://sites.google.com/site/geosaber/_/rsrc/1467172203291/Tutoriais/mapastematicosnoqgis/EE2.png?height=400&width=225)

![](https://sites.google.com/site/geosaber/_/rsrc/1467172203291/Tutoriais/mapastematicosnoqgis/EE3.png?height=400&width=225)

É necessário criar uma conta no serviço do USGS para poder baixar as Imagens.

[![USGS](https://sites.google.com/site/geosaber/_/rsrc/1467172203291/Tutoriais/mapastematicosnoqgis/EarthExplorer_download.png)](http://earthexplorer.usgs.gov/)

Faça o download da Imagem no formato GeoTIFF (padrão OpenGIS para Imagens) e descompacte ela na sua pasta de trabalho. O primeiro passo é fazer a Transformação do Sistema de Coordenadas de Geográficas para UTM (distâncias horizontal e vertical em metros) clicando com o botão direito sobre o nome da Camada > Salvar Como....

[![QGIS](https://sites.google.com/site/geosaber/_/rsrc/1467172203291/Tutoriais/mapastematicosnoqgis/Salvar%20Raster.png)](http://qgis.org/pt_BR/docs/index.html)

É importante se trabalhar com um único SRC nas Camadas e no Projeto quando for fazer processamentos com Camadas Raster. Uma forma fácil de Cortar o Raster (Raster > Extração > Cortador) para o tamanho da sua Área de Interesse é gerar um Polígono a partir da Extensão da Camada... (no menu Vetor > Investigar). Tenha cuidado porque se a Camada de referência para gerar o Polígono for a partir dos DGN o SRC de saída será a UTM em Quilômetros e você terá que converter depois para UTM (metros) para que possa usar como limite de corte do Raster.

[![QGIS](https://sites.google.com/site/geosaber/_/rsrc/1467172203291/Tutoriais/mapastematicosnoqgis/Cortador.png)](http://qgis.org/pt_BR/docs/index.html)

Agora vamos acertar a simbologia do MDE para atribuir cores às faixas de altitude ("hipsometria") entrando na Propriedades da Camada aba Estilo.

[![QGIS](https://sites.google.com/site/geosaber/_/rsrc/1467172203291/Tutoriais/mapastematicosnoqgis/Estilo%20Raster.png)](http://qgis.org/pt_BR/docs/index.html)

Use Banda Simples em Falsa-Cor, e na Cor de Interpolação use Discreto ao invés de Linear para que as quebras entre os intervalos fiquem mais evidenciadas, separando as faixas de cores. Em Gerar Novo Mapa de Cores, primeiro Carregue os Valores de Min/Max (menores e maiores elevações) marcando Min/Max e na Precisão marque Real e clique em Carregar. Volte no Mapa de Cores, escolha a paleta de cores (Red/Yellow/Green) e inverta para que as cores quentes/escuras representem os altos e cores frias/claras os baixos (valores). Defina o número de Classes para dividir os intervalos e clique em Classificar. Na Reamostragem coloque Aproximado: em Bilinear e ausente Média para suavizar a renderização e fechar os vazios, respectivamente. Vá na aba Transparência e mude para 25% de transparência (para poder sobrepor essa Camada ao modelo de Relevo Sombreado). Para gerar o Relevo Sombreado, entre em Raster > Análise do Terreno > Sombreamento...

[![QGIS](https://sites.google.com/site/geosaber/_/rsrc/1467172203291/Tutoriais/mapastematicosnoqgis/Sombreamento.png)](http://qgis.org/pt_BR/docs/index.html)

Mantenha o Relevo Sombreado na base (por baixo das outras Camadas), ele vai criar a impressão de textura 3D. Faltou extrair as Curvas de Nível a partir do MDE, para compor o nosso mapa, faça isso em Raster > Extração > Contorno. O SRTM tem *Erro Vertical Absoluto (90%)* de 16 metros, *Erro Vertical Relativo (90%)* de 10 metros e *Erro Horizontal Absoluto (90%)* de 20 metros*. Porém, em comparação com Pontos de Terreno (*Ground-Truth*) o *Erro Vertical Absoluto (90%)* atingiu 6.2 metros para a América do Sul*. Pelo **PEC**\*\* Altimétrico, Classe A para Cartas Topográficas é de "metade da equidistância das Curvas de Nível" na escala da Carta. Assim sendo, o SRTM fornece a possibilidade de se extrair Curvas de Nível com equidistância de 20 metros (*EVR*: 10 metros) compatível com a Escala 1:50.000 segundo as ***Normas Técnicas da Cartografia Nacional*** (Decreto 89.817/1984)***.

[![QGIS](https://sites.google.com/site/geosaber/_/rsrc/1467172203290/Tutoriais/mapastematicosnoqgis/Contornos.png)](http://qgis.org/pt_BR/docs/index.html)

O truque com as Curvas de Nível é usar uma cor bem escura (preto), espessura de 0,10 e adicionar uma transparência de 60% (inclusive nos Rótulos).

![](https://sites.google.com/site/geosaber/_/rsrc/1467172203291/Tutoriais/mapastematicosnoqgis/Relevo.png?height=305&width=400)

#### 3.2 Imagem Landsat 8

Outra forma interessante de representar o Mapa é usar uma Imagem de Satélite em uma Composição Colorida em que destaque o Uso e Cobertura do Solo. Isso pode ser feito usando uma Composição RGB em falsa-cor onde se substitui a Banda Verde (3 no L8) pelo Infravermelho Próximo (5 no L8).

[![Landsat](https://sites.google.com/site/geosaber/_/rsrc/1467172203291/Tutoriais/mapastematicosnoqgis/landsat8_geoint.png)](http://landsat.usgs.gov/band_designations_landsat_satellites.php)

Vamos baixar o produto *[LandsatLook Images](http://landsat.usgs.gov/LandsatLookImages.php)* que é uma composição colorida em "cor natural" (Bandas 6/SWIR, 5/NIR e 4/Red) georreferenciada.

No serviço [EarthExplorer](http://earthexplorer.usgs.gov/) pode-se usar um Shapefile ou KML para localizar sua Área de Interesse (se você estiver logado).

[![EarthExplorer](https://sites.google.com/site/geosaber/_/rsrc/1467172203291/Tutoriais/mapastematicosnoqgis/EE_shapefile.png)](http://earthexplorer.usgs.gov/)

Faça a busca (*Search Criteria*) pelas Imagens Landsat 8 (*Data Sets* \> L8 OLI/TIRS).

[![USGS](https://sites.google.com/site/geosaber/_/rsrc/1467172203291/Tutoriais/mapastematicosnoqgis/Landsat8.png)](http://earthexplorer.usgs.gov/)

Para trabalhar com Processamento Digital de Imagens deve-se baixar o arquivo completo, com todas as Bandas (faixas do Espectro Eletromagnético) individuais. Neste exercício vamos usar a "*LandsatLook images with Geographic Reference* (10.8 MB)" para servir de Camada de cobertura em nosso Mapa.

[![EarthExplorer](https://sites.google.com/site/geosaber/_/rsrc/1467172203291/Tutoriais/mapastematicosnoqgis/Natural%20Color.png)](http://earthexplorer.usgs.gov/)

Adicione a Camada Raster no QGIS e entre na Propriedades > Estilo para acertar a ordem das Bandas da Imagem (é um arquivo JPG georreferenciado).

[![QGIS](https://sites.google.com/site/geosaber/_/rsrc/1467172203291/Tutoriais/mapastematicosnoqgis/Estilo%20Raster%20L8.png)](http://qgis.org/pt_BR/docs/index.html)

Coloque na ordem: B1 (Red) na Banda Vermelha, B2 (Green) na Banda Verde e B3 (Blue) na Banda Azul e depois vá na Transparência e coloque 25% de transparência na Imagem (para ela se sobrepor ao Relevo Sombreado).

[![Cursos de QGIS](https://sites.google.com/site/geosaber/_/rsrc/1467172203290/Tutoriais/mapastematicosnoqgis/Bauru_L8.png)](http://localhost/wordpress/Cursos)

Apesar de ser uma Composição RGB (que já perdeu muito da informação original), é possível fazer Índices de Vegetação com esta Imagem. Primeiro é preciso transformar a Camada em formato GeoTIFF e multibanda (separada em três bandas) e para isso usaremos a ferramenta Raster > Extração > Cortar (assim já cortamos a Imagem pelo polígono da nossa AI e salvamos o resultado como .TIF). Feito isso, vamos em Raster > Calculadora Raster para poder calcular o Índice de Vegetação por Diferença Normalizada (NDVI).

[![QGIS](https://sites.google.com/site/geosaber/_/rsrc/1467172203291/Tutoriais/mapastematicosnoqgis/NDVI.png)](http://qgis.org/pt_BR/docs/index.html)

Observe que a Imagem transformada para o formato GeoTIFF aparece com as Bandas individualizadas. Sabemos que a Imagem original é um RGB das Bandas 6 (SWIR), 5 (NIR) e 4 (Red) aparecendo no QGIS como Banda 1, Banda 2 e Banda 3 respectivamente. A fórmula para o cálculo do NDVI é ***(NIR -Red) / (NIR + Red)***, resultando em uma Imagem de uma única Banda, que devemos colocar em falsa-cor para podermos diferenciar melhor o resultado.

[![QGIS](https://sites.google.com/site/geosaber/_/rsrc/1467172203291/Tutoriais/mapastematicosnoqgis/Estilo%20Raster%20NDVI.png)](http://qgis.org/pt_BR/docs/index.html)

O resultado pode ser visto em nosso mapa:

![](https://sites.google.com/site/geosaber/_/rsrc/1467172203290/Tutoriais/mapastematicosnoqgis/Bauru_L8_NDVI.png)

Com a Reclassificação, será possível contar os pixels (para saber a área de cada Classe) ou converter para Polígonos.

### 4\. Compositor de Impressão (layout do Mapa)

No QGIS é possível criar várias composições de mapa (*layout*) dentro de um mesmo Projeto, por isso a primeira coisa que ele pede é o nome do Mapa. Insira o *Frame* (caixa que conterá o Mapa) na Folha de papel que é exibida, lembrando de deixar espaço das margens e para poder adicionar legendas e outros Itens. Antes de você começar precisa observar se o seu Sistema de Referência de Coordenadas está na forma Geográfica (graus) ou Plana (metros). Quando você cria uma nova Grade deve definir o SRC (ou deixe que o Compositor irá usar o do seu Projeto), lembrando que é possível ter duas Grades, em SRC diferentes (como nas Cartas do IBGE, onde as bordas são em Geográficas e as linhas internas estão em UTM). O intervalo da Grade deve ser definido tendo em mente o SRC (1° = 111,11km e as zonas UTM tem 6° de largura) e a Escala (1:1.000 significa que 1mm são 1 metro, então se por linhas de coordenadas a cada 1 metro, elas ficarão com 1mm de distância no Mapa dentro do Compositor). No meu exemplo, o SRC é UTM 22S (portanto, metros são as unidades do mapa - que pede em 'Unidades do Intervalo') e a Escala é 1:100.000, ou seja 1mm é 100 metros e 1cm é igual a 1.000 metros. Como a folha é A4 (21x29cm), eu usei 10.000 metros como Intervalo (uma linha a cada 10 centímetros).

![](https://sites.google.com/site/geosaber/_/rsrc/1467172203290/Tutoriais/mapastematicosnoqgis/Compositor1.png)

Configurando a Escala:

![](https://sites.google.com/site/geosaber/_/rsrc/1467172203291/Tutoriais/mapastematicosnoqgis/Escala.png)

(este Capítulo ainda está em construção...)

### 5\. Referências

-[Noções de Cartografia](http://www.ibge.gov.br/home/geociencias/cartografia/manual_nocoes/elementos_representacao.html)
-[http://www.concar.ibge.gov.br/detalheDocumentos.aspx?cod=8](http://www.concar.ibge.gov.br/detalheDocumentos.aspx?cod=8)
-[http://www.gitta.info/TerrainAnalyi/en/html/index.html](http://www.gitta.info/TerrainAnalyi/en/html/index.html)
-[http://www2.jpl.nasa.gov/srtm/SRTM_D31639.pdf](http://www2.jpl.nasa.gov/srtm/SRTM_D31639.pdf)
-[http://landsat.usgs.gov/documents/Landsat8DataUsersHandbook.pdf](http://landsat.usgs.gov/documents/Landsat8DataUsersHandbook.pdf)
-[Remote Sensing Methods](http://wiki.landscapetoolbox.org/doku.php/remote_sensing_methods:home)
-[HTML to Markdown](http://domchristie.github.io/turndown)

### [![Attribution-NonCommercial-NoDerivatives 4.0 International (CC BY-NC-ND 4.0)](https://sites.google.com/site/geosaber/_/rsrc/1467172203291/Tutoriais/mapastematicosnoqgis/Creative-Commons_XS1-300x105.jpg)](http://creativecommons.org/licenses/by-nc-nd/4.0)

Este obra está licenciada sob a Licença [Creative Commons Atribuição-NãoComercial-SemDerivações 4.0 Internacional](http://creativecommons.org/licenses/by-nc-nd/4.0/).

### Licenças Creative Commons:

-   ![Attribution](https://upload.wikimedia.org/wikipedia/commons/thumb/3/3c/Cc-by_new.svg/40px-Cc-by_new.svg.png) **Atribuição** (BY): Os licenciados têm o direito de copiar, distribuir, exibir e executar a obra e fazer trabalhos derivados dela, conquanto que dêem créditos devidos ao autor ou licenciador, na maneira especificada por estes.

-   ![Non-commercial](https://upload.wikimedia.org/wikipedia/commons/thumb/d/db/Cc-nc.svg/40px-Cc-nc.svg.png) **Uso Não comercial** (NC): Os licenciados podem copiar, distribuir, exibir e executar a obra e fazer trabalhos derivados dela, desde que sejam para fins não-comerciais.

-   ![Non-derivative](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c7/Cc-nd.svg/40px-Cc-nd.svg.png) **Não a obras derivadas** (ND): Os licenciados podem copiar, distribuir, exibir e executar apenas cópias exatas da obra, não podendo criar derivações da mesma.

-   ![Share-alike](https://upload.wikimedia.org/wikipedia/commons/thumb/2/29/Cc-sa.svg/40px-Cc-sa.svg.png) **Compartilhamento pela mesma licença** (SA): Os licenciados devem distribuir obras derivadas somente sob uma licença idêntica à que governa a obra original. (Veja também: [copyleft](https://pt.wikipedia.org/wiki/Copyleft "Copyleft").)
