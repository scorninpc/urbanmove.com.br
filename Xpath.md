# XPath

## Exemplos Práticos

### Link

https://www.portalzuk.com.br/imovel/sp/sao-paulo/bras/avenida-alcantara-machado-2978/26961-172938

### Capturando o texto uma classe

`<h1 class="title">Apartamento à venda em leilão</h1>`

//h1[@class = 'title']

//*[@class = 'title']

### Capturando o texto um ID

`<span id="maior-lance-vlr">0,00</span>`

//span[@id = 'maior-lance-vlr']

//*[@id = 'maior-lance-vlr']

### Capturando um Atributo de Filhos
```html
<figure class="box-action-bank">
<a href="https://www.portalzuk.com.br/leilao-de-imoveis/v/leilao-judicial-sao-paulo-tjsp"> 
<img src="https://imagens.portalzuk.com.br/comitentes/76cf0a7ec37e4a04ec2a614a453fa4a4.webp" alt="Tribunal de Justiça do Estado de São Paulo">
</a>
</figure>
```
//figure[@class="box-action-bank"]/a/@href

//*[@class="box-action-bank"]//@href

//*[@class="box-action-bank"]/a/img/@src

//figure[@class="box-action-bank"]//img/@src

//figure[@class="box-action-bank"]//@alt

< asdas > 

