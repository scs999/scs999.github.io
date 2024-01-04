# Leaflet Maps with Google Sheets
Customize Leaflet maps with a linked Google Sheets template or CSV files and GeoJSON data on GitHub

![Preview](navigation.png)

## Live links
- Mapa https://scs999.github.io/Mapa_Local/
- Planilha [https://docs.google.com/spreadsheets/d/1G1H7zEI8HHBL16Tw0bkTWrKUnBnRe3k2gcmn7xupTBM/edit#gid=0](https://docs.google.com/spreadsheets/d/1-GwANoUOCefOw_Uljv7Ul66BLaU15sfRGTMjVYVoJFA/edit#gid=670446197)

## Create your own
See step-by-step tutorial in *Hands-On Data Visualization* https://handsondataviz.org/leaflet-maps-with-google-sheets.html

#### Geocode your address data with Google Sheets add-on
To geocode (find latitude and longitude coordinates), we recommend installing the free [Geocoding by SmartMonkey add-on for Google Sheets](https://gsuite.google.com/marketplace/app/geocoding_by_smartmonkey/1033231575312). Insert your addresses in place of the samples in the Geocoding Details tab, then use Add-Ons > Geocoding > Geocode Details menu. Learn more in *Hands-On Data Visualization* https://handsondataviz.org/geocode.html

![Geocoding](geocode.png)

#### To finalize your map, you need to either:
- Download each Google Sheets tab as a CSV file and upload into a `csv` subfolder in your GitHub repo
  - OR
- Get your own Google Sheets API Key to insert into `google-doc-url.js`

See Steps G or H in the tutorial https://handsondataviz.org/leaflet-maps-with-google-sheets.html

## Update your code for any pre-October 2020 maps before January 2021
If you used our code to create a map prior to October 2020, you will need to update your version before January 26, 2021 for it to continue to work. Google announced that it will [migrate from Google Sheets API v3 to v4 in Jan 2021](https://developers.google.com/sheets/api/v3), and we updated our code to v1.2 on September 29th to address Google's changes.

Quatro opções para atualizar seu código:

Opção A: 
use seu código existente e extraia seus dados de arquivos CSV em vez de uma planilha do Google vinculada. Isso evita a necessidade de uma chave de API do Planilhas Google, mas não aproveita nossas outras atualizações de código.
1. Vá para sua Planilha Google vinculada e, para cada guia, *Arquivo > Baixar* em formato CSV e renomeie-os desta forma: Options.csv, Points.csv, etc.
2. Faça login na interface da web do seu repositório de mapas GitHub.
3. Crie uma nova subpasta chamada `csv` em seu repositório GitHub, selecionando *Adicionar arquivo > Criar um arquivo* e digitando `csv/`. A barra indica que é uma pasta, não um arquivo.
4. Em seu repositório GitHub, carregue cada arquivo CSV criado nesta nova subpasta `csv`.
5. Em seu repositório Github, abra o arquivo `google-doc-url.js`, vá até o final da página e exclua-o.
Agora o código procura automaticamente dados na sua pasta CSV, em vez de na Planilha Google. Se desejar, você pode continuar usando a Planilha Google para editar o conteúdo do seu mapa e carregar essas alterações sempre na pasta CSV ou editar os arquivos CSV diretamente.

Opção B: 
se você entende (ou deseja aprender) [GitHub Desktop](https://handsondataviz.org/github-desktop-atom.html), use-o para mover cópias do código mais recente (index.html, pasta de scripts, style.css, etc.) em seu repositório por meio de seu computador local. No arquivo `google-doc-url.js`, copie e cole a chave da API do Planilhas Google que aparece na metade inferior do nosso código, mas mantenha seu próprio ID do Planilhas Google que aparece na metade superior do seu código.

Opção C:
se você originalmente "forkou" uma cópia de nosso código, crie uma "solicitação pull" do GitHub para atualizar seu repositório com nossas revisões de código, incluindo a chave da API do Planilhas Google. Recomendamos esta opção apenas se você entender (ou estiver disposto a aprender sobre) pull requests do GitHub e puder lidar com a resolução de conflitos entre seu código e nosso código atualizado.
Aviso: Como esta operação pode substituir parte do seu código, vá para *Código > Baixar ZIP* para fazer um backup em seu computador local.
1. Faça login na interface da web do repositório de mapas históricos do GitHub.
2. Clique em *Solicitações pull* e clique no botão verde para uma *Nova solicitação pull*.
3. Na página *Comparando alterações*, use os menus para extrair o código *para* seu repositório *do* repositório original, denominado HandsOnDataViz/leaflet-maps-with-google-sheets. O GitHub pode avisar que você não pode mesclar os arquivos automaticamente, mas prossiga mesmo assim.
4. Talvez seja necessário clicar no botão *Resolver conflitos* na próxima tela, o que significa que você precisa decidir quais partes do seu código manter e quais partes do nosso código aceitar. De modo geral, você deve aceitar nossas atualizações para index.html, style.css e a maioria dos scripts.js, enquanto mantém seu próprio conteúdo para README.md, mídia e conteúdo da pasta geojson. No arquivo google-doc-url.js, você deve manter seu próprio ID do Planilhas Google, mas adicionar temporariamente nossa chave de API do Planilhas Google até criar a sua própria. No GitHub, você pode resolver conflitos de código excluindo/mantendo linhas em arquivos específicos.

Opção D:
recomeçar com um repositório totalmente novo e migrar o conteúdo do mapa existente. Faça uma cópia do nosso código mais recente clicando no botão verde ‘Usar modelo’. Migre qualquer conteúdo de pasta de mídia ou pasta de dados geográficos do seu repositório antigo para o novo, baixando-o para o seu computador local e carregando-o no GitHub. Reconecte seu ID da Planilha Google ao arquivo `google-doc-url.js` em seu novo repositório.

## Credits (and licenses)
Developed by [Ilya Ilyankou](https://github.com/ilyankou) and [Jack Dougherty](https://github.com/jackdougherty) with support from Trinity College CT. Inspired by Code for Atlanta mapsfor.us (2016) https://github.com/codeforatlanta/mapsforus (BSD-3-Clause)

We use [Google Sheets API version 4](https://developers.google.com/sheets/api), with these open-source components:

- Leaflet v1.7.1 https://leafletjs.com (BSD-2-Clause)
- jQuery v3.5.1 https://code.jquery.com (MIT)
- PapaParse v5.3.0 to parse CSV with JavaScript (MIT)
- Font Awesome (v4.7) https://cdn.fontawesome.com (MIT, SIL OFL 1.1)
- leaflet-providers (v1.10.2) https://github.com/leaflet-extras/leaflet-providers (BSD-2-Clause)
- Leaflet.awesome-markers (v2.0.4), manually updated to svg to allow hex and material icons https://github.com/sigma-geosistemas/Leaflet.awesome-markers (MIT)
- Leaflet.markercluster (v1.4.1) https://github.com/Leaflet/Leaflet.markercluster (MIT)
- Leaflet.MarkerCluster.LayerSupport (v.2.0.1) https://github.com/ghybs/Leaflet.MarkerCluster.LayerSupport (MIT)
- Leaflet Control Geocoder v1.13.0 https://github.com/perliedman/leaflet-control-geocoder (BSD 2-Clause)
- leaflet-locatecontrol (v0.72.0) https://github.com/domoritz/leaflet-locatecontrol (MIT)
- jQuery-CSV (v1.0.11) https://github.com/evanplaice/jquery-csv (MIT)
- DataTables (v1.10.22) by SpryMedia Ltd. https://datatables.net (MIT)
- Material icons https://material.io/resources/icons/ (Apache)
- Single Element CSS Spinner (31 May 2016) https://github.com/lukehaas/css-loaders (MIT)
- Google Colour Palette Generator (2015) https://github.com/google/palette.js (MIT)
- polylabel (Dec. 2016 customized) https://github.com/mapbox/polylabel to optimally place text labels in a polygon (ISC), with TinyQueue (v1.1.0) (https://github.com/mourner/tinyqueue), polylabel's dependency (ISC)
