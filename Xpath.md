# XPath

## Exemplos Práticos

### Link

https://www.portalzuk.com.br/imovel/sp/sao-paulo/bras/avenida-alcantara-machado-2978/26961-172938

### Capturando o texto uma classe

`<h1 class="title">Apartamento à venda em leilão</h1>`

//h1[@class = 'title']

//*[@class = 'title']

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/b52d1965-6fe5-45e9-8a0a-0a3bbef280de)


### Capturando o texto um ID

`<span id="maior-lance-vlr">0,00</span>`

//span[@id = 'maior-lance-vlr']

//*[@id = 'maior-lance-vlr']

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/e3698f3a-da4c-457f-9945-f37c840699cc)


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

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/dfebce97-14c6-473a-8191-f39cf7aca9a0)


### Vetores

``` html
<div class="property-documents-items">

<a class="property-documents-item" href="https://documentacaoleilao.portalzuk.com.br/2023/05/14f3d4f29ca2b539d929a71a4ea46fd2.pdf" target="_blank">
<span class="property-documents-item-icon"></span>
<span class="property-documents-item-label">Edital de venda</span>
</a>

<a class="property-documents-item" href="https://documentacao.portalzuk.com.br/I27830lote001divida_ativa.pdf" target="_blank">
<span class="property-documents-item-icon"></span>
<span class="property-documents-item-label">Dívida Ativa</span>
</a>

<a class="property-documents-item" href="https://documentacao.portalzuk.com.br/I27830lote001matricula2.pdf" target="_blank">
<span class="property-documents-item-icon"></span>
<span class="property-documents-item-label">Matricula do Imóvel</span>
</a>

</div>
```

//div[@class="property-documents-items"]/a[position()=2]/@href

//div[@class="property-documents-items"]/*[@class="property-documents-item"][position()=2]/@href

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/5cfe31dd-a454-4513-bb4b-a02273301d1c)








## Até aqui podemos observar:

A captura de um elemento deve começar com `//TAG`, o que pode ser substituído por `//*` em locais que possuem outras referências únicas

Chamamos de seletor Tag, ID, Class, etc

`Seletor A / seletor B` retorna o Seletor B que é filho direto do Seletor A

`Seletor A // seletor B` retorna o Seletor B que é filho do Seletor A, não importando se é direto.

href, alt, src são atributos e quando precisamos obter seus valores devemos utilizar `@nome_do_atributo`  

Quando queremos capturar um elemento dentro de um vetor, ou seja, quando existem vários elementos com o mesmo seletor e queremos uma posição específica devemos utilizar `[position()=n]` onde o n é a posição desejada

