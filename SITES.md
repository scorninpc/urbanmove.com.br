- [x] [portalzuk.com.br](#portalzukcombr)
- [x] [jeleiloes.com.br](#jeleiloescombr)
- [x] [megaleiloes.com.br](#megaleiloescombr)
- [x] [alfaleiloes.com](#alfaleiloescom)
- [x] [webleiloes.com.br](#webleiloescombr)
- [ ] Paulo Botelho Leiloeiro
- [ ] leilaobrasil.com.br)
- [ ] d1lance
- [ ] destakleiloes
- [ ] [superbid.net](#superbidnet)
- [ ] Multiplique Leilões
- [ ] satoleiloes
- [ ] topoleiloes
- [ ] agsleiloes
- [ ] casareisleiloes
- [ ] frazaoleiloes
- [ ] Viva Leilões (vivaleiloes.com.br)
- [ ] lancejudicial
- [ ] oleiloes
- [ ] leje
- [ ] gaialeiloes
- [ ] pecinileiloes
- [ ] sublimeleiloes
- [ ] amaralleiloes
- [ ] BCO Leilões (bcoleiloes.com.br)
- [ ] Biasi Leilões
- [ ] imoveis.bancointer
- [ ] Kronberg Leiloes
- [ ] LUT Leilões
- [ ] teza
- [ ] leilaovip.com.br
- [x] [visar.com.br](#visarcombe)
- [x] [lancenoleilao.com.br](#lancenoleilaocombr)

# roteiro para novos sites

- verificar se tem /sitemap.xml
	- se tiver sitemap.xml, ele será a `url de paginação`, e o `tipo de paginação` será `Sitemap`
	- se não tiver sitemap.xml, verificar qual a tela que faz a listagem dos lotes ou leilões
		- se essa tela tiver botões de paginação, verificar se ao clicar, é carregado uma nova pagina, com o numero da pagina na url
			- se sim, essa url deverá ser adicionada no campo `url de paginação`, e onde tem o numero da pagina, deve ser colocado `{pagina}` e o `tipo de paginação` deve ser `Normal`
			- se não mudar a url, e só carregar novos lotes, precisa apertar `F12` e ir na aba `Rede` ou `Network` e mudar para outra pagina. Nessa tela irá exibir um carregamento `ajax`. Essa url é a `url de paginação` e o `tipo de paginação` deve ser `Ajax`
		- se essa tela não tiver botões de paginação, verificar se ele carrega mais ao rolar até o final da pagina.
			- se ele carrega mais ao rolar até o final, ou tem um botão `carregar mais`, precisa apertar `F12` e ir na aba `Rede` ou `Network` e clicar ou rolar para nova pagina. Nessa tela irá exibir um carregamento `ajax`. Essa url é a `url de paginação` e o `tipo` deve ser `Ajax`

# portalzuk.com.br

- site sem sitemap
- não possui pagina para o leilão, já é lote direto
- a paginação é feita por "carregar mais" (precisa ver no console, qual o endereço do ajax, e qual os parametros enviado por post)
- na pagina inicial, usar a pagina que lista os lotes `https://www.portalzuk.com.br/leilao-de-imoveis`
- url da paginação `https://www.portalzuk.com.br/leilao-de-imoveis/mais`
- a pagina do leilão, é usada como cidade. Então pode-se ignorar a pagina do leilão, já que alistagem ja mostra o lote direto. Deixar o campo do leilão em branco
- o ajax para recuperar mais, rpecisa enviar um token, que está no campo input `name="_token"`. Logo, o campo "data paginação" precisa desse token, e pode ser recuperado com
```
'limit={offset}&count_imovel_zuk={offset}&path=https%3A%2F%2Fwww.portalzuk.com.br%2Fleilao-de-imoveis&order=uf_cidade&div_parceiro_count=0&_token='+document.getElementsByName('_token')[0].value
```
- o site usa alguns caracteres inválidos na url, como `º` e `°` (que parecem ser o mesmo, mas não é). Ficar atento para ver se tem mais algum caractere inválido para buscar


# jeleiloes.com.br

- site sem sitemap
- a busca vazia traz todos os lotes, o que pode ser usado como tela para listar todos os lotes
- não tem leilão, ja exibe o lote direto, podendo deixar o campo "URL Leilão" do painel em branco
- o site usa paginação simples, paginação tipo NORMAL
- como é paginação normal, quantidade e dados da paginação podem ficar em branco
- a url usada para paginação é a `https://www.jeleiloes.com.br/busca?busca=&page={pagina}`
- a url do lote é composta por `https://www.jeleiloes.com.br/oferta/leilao/{categoria}/{subcategoria}/{codigo}/{outrocodigo}/{slug}`

# megaleiloes.com.br

- site sem sitemap
- ~~o site usa ajax para as paginações, então deve usar delay para poder usar a api do browsershot~~
- apesar de usar ajax, se for por categorias, é possivel utilizar a url `https://www.megaleiloes.com.br/imoveis?pagina=2` direto no campo url de paginação, e fazer o bypass do ajax
- esse site nao tem uma tela com leilão e os lotes dentro, ele usa os lotes direto na listagem, então podemos deixar o padrão de url do leilão em branco
- o site usa paginação simples, paginação tipo NORMAL
- na url do lote, o id fica no final, então podemos usar o padrão de url `https://www.megaleiloes.com.br/imoveis/{subcategoria}/{estado}/{cidade}/{slug}-{codigo}`

# alfaleiloes.com

- site sem sitemap
- está configurado para usar browsershot com 2 segundos de delay, mas não vi necessidade
- padrão para paginação é `https://www.alfaleiloes.com/leiloes/todas-as-modalidades?pagina={pagina}`
- paginação pode ser usada normal
- esse site nao tem uma tela com leilão e os lotes dentro, ele usa os lotes direto na listagem, então podemos deixar o padrão de url do leilão em branco
- um bom padrão de url de lote seria `https://www.alfaleiloes.com/leilao/lote/{codigo}/{slug}`

# webleiloes.com.br

- site precisa rodar com delay, pois ele utiliza ajax, que possui aqueles icones de "loading"
- o site possui sitemap.xml, o que agiliza e facilita a busca. Existem 225 lotes no momento dessa analise.
- a url do sitemap foi utilizada no campo `URL Paginação`
- o campo `Tipo Paginação` foi setado como `Sitemap`
- como recuperaremos o link do lote direto, pode deixar o campo `URL Leilão` em branco
- o campo `URL Lote` deve ter o padrão `https://www.webleiloes.com.br/lote/{slug2}/{slug1}`
- esse sitemap ja possui a tag address, que ja possui latitude e longitude, imagens, cidade, e tudo mais

# superbid.net

- site sem sitemap
- a url inicial estava como "www.superbid.net " com aspas e sem o protocolo https
- evento é o leilão
- oferta é o lote
- a paginação possui campo para "quantos por pagina". Sendo assim, da pra puxar um numero exorbitante por pagina, que o site fica sem paginação. é mais rapido e mais confiavel

https://www.superbid.net/oferta/{slug}


# visar.com.br

- precisa dar o parse no html, em busca do `onclick="abrirDetalhesLeilao('XXXXXX');"` e ai montar a URL `https://ssl1.visar.com.br/leiloeirolegentil.com.br/Leilao.asp?zz=XXXXX`
- esses cassos são raros, precisa levantar quais os casos de desvios, e é muito mais simples fazer um `IF(dominio)` e tratar a URL nesse dominio dentro de `getHrefs()`
- como nao tem leilão, e ja é o lote direto, o campo leilão ficou fazio
- usado a variavel 1 no padrão da URL do lote: `substring-before(substring-after((//div[contains(@onclick, 'abrirDetalhesLeilao')]/@onclick)[n], "'"), "'")`

# lancenoleilao.com.br

- a paginação estava errada, sem informar a {pagina}
- precisa dar o parse no html, em busca do `goTo('loteVendaDireta.php?idLote=12744');"` e ai montar a URL `https://lancenoleilao.com.br/loteVendaDireta.php?idLote=12744`
- tipo de paginação estava ajax, mas não é carregado via ajax
- o site não é carregado via ajax, e nem por javascript, então removi o 2s de delay e coloquei somente 1s
- como nao tem leilão, e ja é o lote direto, o campo leilão ficou fazio
- usado a variavel 1 no padrão da URL do lote: `substring-before(substring-after((//div[contains(@onclick, 'lote.php')]/@onclick)[n], "="), "'")`

