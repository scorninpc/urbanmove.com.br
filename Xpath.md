# XPath

# Exemplos Práticos

# Funções Básicas 

### Link

https://www.portalzuk.com.br/imovel/sp/sao-paulo/bras/avenida-alcantara-machado-2978/26961-172938

### Teste dos comandos no console do navegador

`$x("comando XPath")`

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/a9e8fbd8-7c10-47be-bccf-c0687a789c76)


## Capturando o texto uma classe

`<h1 class="title">Apartamento à venda em leilão</h1>`

//h1[@class = 'title'] 

//*[@class = 'title']

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/b52d1965-6fe5-45e9-8a0a-0a3bbef280de)

#### A captura de um elemento deve começar com `//TAG`, o que pode ser substituído por `//*` em locais que possuem outras referências únicas


## Capturando o texto um ID

`<span id="maior-lance-vlr">0,00</span>`

//span[@id = 'maior-lance-vlr']

//*[@id = 'maior-lance-vlr']

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/e3698f3a-da4c-457f-9945-f37c840699cc)


## Capturando um Atributo de Filhos
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

#### Chamamos de seletor Tag, ID, Class, etc

#### Seletor A / seletor B` retorna o Seletor B que é filho direto do Seletor A

#### Seletor A // seletor B` retorna o Seletor B que é filho do Seletor A, não importando se é direto.

#### href, alt, src são atributos e quando precisamos obter seus valores devemos utilizar `@nome_do_atributo`  


## Vetores
### Exemplo 01
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

//div[@class="property-documents-items"]/*[@class="property-documents-item"][2]/@href

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/a39f8471-1aa8-4d1b-9968-cde96a49eb8a)

### Exemplo 02

``` html
<ul class="card-action-items">
          <li class="card-action-item">
            <div class="card-action-item-type-bid">
                    Lance mínimo:
            </div>
        </li>
        <li class="card-action-item">
            <div class="card-action-item-content">
                <span class="card-action-item-text ">1º Leilão</span>
                <span class="card-action-item-date">
                    <s>
                        15/06/23 às 10h40
                    </s>
                </span>
            </div>
                <span class="card-action-item-value">R$ <s>418.190,84</s></span>
        </li>
        <li class="card-action-item">
            <div class="card-action-item-content">
                <span class="card-action-item-text">2º Leilão</span>
                <span class="card-action-item-date">07/07/23 às 10h40</span>
            </div>
              <span class="card-action-item-value">R$ 250.914,51</span>
        </li>
</ul>
```
//*[@class = 'card-action-items']//span[1]
#### Retorna todos os spans que estão em 1º lugar dentro de seus Tags

//*[@class = 'card-action-items']//span[2]
#### Retorna todos os spans que estão em 2º lugar dentro de seus Tags

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/1ff22466-4613-41d2-8d7a-a957f09eb4e2)

//*[@class = 'card-action-items']//li[1]

//*[@class = 'card-action-items']//li[2]

//*[@class = 'card-action-items']//li[3]

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/1a4fb671-024d-4cf2-bd99-e98d9811d24d)

//*[@class = 'card-action-items']//li[2]//span[1]

//*[@class = 'card-action-items']//li[2]//span[2]

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/6d86234c-0c4f-4f67-9596-bf992737bad4)











#### Quando queremos capturar um elemento dentro de um vetor, ou seja, quando existem vários elementos com o mesmo seletor e queremos uma posição específica devemos utilizar `[position()=n]` ou apenas [n] onde o n é a posição desejada

## Funções de Pesquisa e Deslocamento

``` html
<ul class="card-action-items">
          <li class="card-action-item">
            <div class="card-action-item-type-bid">
                              Lance mínimo:
                          </div>
          </li>
          <li class="card-action-item">
              <div class="card-action-item-content">
                    <span class="card-action-item-text ">1º Leilão</span>
                    <span class="card-action-item-date">
                              <s>
                                        15/06/23 às 10h40
                              </s>
                    </span>
              </div>
              <span class="card-action-item-value">R$ <s>418.190,84</s></span>
          </li>
          <li class="card-action-item">
              <div class="card-action-item-content"><span class="card-action-item-text">2º
              Leilão</span><span class="card-action-item-date">07/07/23 às 10h40</span></div>
              <span class="card-action-item-value">R$ 250.914,51</span>
          </li>
                    
</ul>
```

//div[contains(text(),'Lance mínimo:')]

//*[contains(text(),"Lance m")] * Por hora temos que utlizar Lance m, por hora não estão funcionando todos os caracteres

//ul[.//div[contains(text(),'Lance m')]]

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/e0180f33-cde3-4a8a-a0e8-0aadb6515f32)

#### O operador /.. é usado para navegar para o elemento pai direto. Portanto, essa expressão XPath selecionará o elemento div pai do div que contém o texto "1º Leilão:".

//li[@class = 'card-action-item']//span[contains(text(),'Leil')]

//li[@class = 'card-action-item']//span[contains(text(),'Leil')]/..

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/0d546ce4-b369-48a8-ae2c-979b85db2ee4)






#### A expressão completa //ul[.//div[contains(text(),'Lance mínimo:')]] busca por um elemento ul que contenha um div em qualquer nível de profundidade que tenha o texto "Lance mínimo:".

//ul[.//div[contains(text(),'Lance m')]]/li/div

//ul[.//div[contains(text(),'Lance m')]]//div







![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/e784761a-49c5-49e9-946c-6d9e1e152998)

 



## Funções de Texto
