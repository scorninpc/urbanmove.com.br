# Documentação

## Tutoriais
Github: https://youtu.be/cFgAEJdoYO8

Comandos Básicos e Conceito de Filho: https://youtu.be/waQL1z-i66A

Vetores e Parent: https://youtu.be/osQjGJj7FfE

Continuação Parent e Contains: https://youtu.be/G8ee5WAUnkg

Cadastro de sites: https://youtu.be/q2n6GNkcuLE

Exemplo Agostinho Leilões: https://youtu.be/tGqahpgznCw

Exemplo OA Leilões: https://youtu.be/m5yuQJqXyPM

Errata:
Para buscar um segundo elemento com o contains, está sendo implementado o :next(), o :nth-child() como foi dito no vídeo não funciona

## Padrão de Dúvida

### Título:

Escrever o nome do leiloeiro

### Texto:

1) Escrever a URL em que está sendo feito o teste
    
    Exemplo: https://www.d1lance.com.br/lote/sao-bernardo-do-campo-sp/5447/
    
![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/4958736f-da2a-4456-b673-8755014fb208)

2) Escrever as observações, exemplo:

   Observação 01: O preço está com a data

   Observação 02: O endereço está na descrição

4) Escrever os erros com as variável que não funcionou e o que você tentou, exmeplo:
    
   Erro 01: Documento01: .dg-lote-documentos-downloads

5) Print da tela em que buscou a informação

    Erro 01:    
![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/9c4d9a49-9dcd-4535-8828-5a9c476fe1f9)

    
## CSS

### Básico

1) Extraindo texto de uma class: `.escreva_a_class`

2) Extraindo texto de um id: `#escreva_o_ID`
 
3) Extraindo texto de um tag: `escreva_o_Tag`
 
4) Extraindo Atributo do selector
    Os atributos src e href são capturados automaticamente, para os demais utilizar:
    `escreva_o_selector:attr(escreva o atributo)`

5) Quando precisar extrair o texto de um código com src ou href utilizar:
    `escreva_o_selector:text`

### Conceito de Filho
"Filho" é o que está dentro da Tag.
A Tag é aberta com `<>` e fechada com `</>`, exemplo `<li></li>` 

7) Quando no comando de busca é utilizado o simbolo `>`, com em `div > span > ul`, ele busca o filho que está ligado diretamente ao         "Pai", ou seja ele vai procurar diretamente o `ul`, ligado ao `span` ligado ao `div`.

8) Quando no comando de busca NÃO é utilizado o simbolo `>`, com em `div span ul`, ele busca em tudo dentro do pai, ou seja ele vai     procurar todos os `ul` que estejam dentro de qualquer `span` dentro do `div`, ou seja o `span` não precisa estar diretamente ligado ao `div`, e o `ul` não necessáriamente ligado ao `span`.

Exemplo do item 7 e 8: 

```html
<div>
    <span>  
        <ul> "Filho direto do span"
            <li></li>
        </ul>
    </span>
    
    <ul> "Filho direto da div"
        <li>
            <a></a>
        </li>
    </ul>
    
</div>
```

- O seletor `div ul` vai retornar a `UL` dentro do primeiro elemento que é o "Filho direto do span"
- O seletor `div > ul` só vai pegar o `UL` que é filho direto da `DIV`. 
- O seletor `div > span > ul` vai pegar o `UL` de dentro do `SPAN`, porque o `UL` é filho direto do `SPAN`, que é filho direto do `DIV`

  ### Vetores
  Quando existir mais de um resultado para a busca, deve ser indicado qual o item que se deseja bucar, o 1º, 2º...
  Para isso deve ser utilizado o `:nth-child(escreva_a_posição)` após a `classe`, `id`, `tag` desejado, como abaixo

9) Extraindo texto de um vetor
    `.escreva_a_class:nth-child(escreva_a_posição)`
 
10) Extraindo atributos de um vetor
    `.escreva_a_class:nth-child(escreva_a_posição):attr(escreva o atributo)`

Exemplos de vetores :
    
```html
<div>
    <span>  
        <ul> "Filho direto do span"
            <li>
                <a></a>
            </li>
        </ul>
    </span>
    
    <ul> "Filho direto da div"
        <li>
            <a></a>
            <a></a>
        </li>
    </ul>
    <ul>
        <a></a>
        <a></a>
        <a></a>
    </ul>
</div>
```

- O seletor `div ul` vai retornar as `UL` dentro do primeiro elemento, ou seja o  "Filho direto do span"

  O seletor `div > ul` só vai pegar as duas `UL` que são filhos direto da `DIV`.
- Neste caso o seletor `div > ul:nth-child(1)` vai retornar a segunda `UL`
- E o seletor `div > ul:nth-child(2)` vai retornar a terceira `UL`

O seletor `div a` vai pegar apenas `A` que estão dentro do primeiro elemento da `DIV`, o `span`.
O seletor `div ul a` continua pegando o `A` que estão dentro do `span` `UL`.
O seletor `div > ul a` pegará o `A` que estão dentro da `UL` filha direta da `div`.
O seletor `div > ul:nth-child(2) a` pegará o `A` que estão dentro da segunda `UL` filha direta da `div`.
O seletor `div > ul:nth-child(2) a:nth-child(3)` pegará o terceiro `A` que está dentro da segunda `UL` filha direta da `div`.


 ### Utilizando o Parent
 
```html
 <li class="card-action-item">
              <div class="card-action-item-content">
                <span class="card-action-item-text ">Data</span>
                <span class="card-action-item-date">
                  21/06/23 às 14h04
                </span>
              </div>
              <span class="card-action-item-value">R$ 136.000,00</span>
          </li>
```
12) Neste exemplo acima é fácil capturar os elementos, pois todos tem class, então fica fácil para explicar o conceito de "pai" ou "parent".
Para capturar o texto "Data", podemos utilizar `.card-action-item-text`, para irmos para o seletor acima dele, o `card-action-item-content`, podemos escrever `.card-action-item-content` ou utilizar `.card-action-item-text:parent`, muitas vezes essa será a única solução para capturarmos elementos.

Neste mesmo exemplo para capturar preço a partir da class da "Data". Podemos utilizar 
`.card-action-item-text:parent:parent > span`


### Busca de Texto na Página

13) Podemos ancorar nossa busca a uma palavra com o uso do `contains`, no exemplo acima, poderíamos buscar o seletor que contém a palavra "Data" utilizando:
`span:contains("Data")`, pode ser que tenha outros spans com a palavra Data, então é recomendado se posível indicar algum id ou class antes, como `.card-action-item span:contains("Data")`

Se eu quiser capturar o preço a partir da palavra "Data"
`span:contains("Data"):parent:parent > span`

Se for a segunda vez que o texto "Data" aparece dentro do código
`span:contains("Data"):next(2)` Em implementação!!!

## XPATH

Para selecionar elementos com base em uma classe, substitua "tag" por "*[@class='nome-da-classe']". Por exemplo:
Para selecionar elementos com a classe "exemplo", use "//*[@class='exemplo']".

Para selecionar elementos com base em um ID, substitua "tag" por "*[@id='nome-do-id']". Por exemplo:
Para selecionar o elemento com o ID "exemplo", use "//*[@id='exemplo']".

//tag: Seleciona todos os elementos com a tag especificada, independentemente de sua localização no documento.
//tag[@atributo='valor']: Seleciona elementos com a tag especificada que possuem um atributo com um determinado valor.
//tag/text(): Retorna o texto contido dentro dos elementos com a tag especificada.
//tag[contains(text(),'texto')]: Seleciona elementos com a tag especificada que contêm o texto fornecido.
//tag1/tag2: Seleciona elementos da tag2 que são descendentes diretos da tag1.
//tag1//tag2: Seleciona elementos da tag2 que são descendentes (diretos ou indiretos) da tag1.
//tag[position()=n]: Seleciona o n-ésimo elemento da tag especificada.
//tag[last()]: Seleciona o último elemento da tag especificada.
//tag1[@attr1='valor1' and @attr2='valor2']: Seleciona elementos com a tag1 que possuem os atributos e valores especificados.
//tag1 | //tag2: Seleciona elementos da tag1 e da tag2.
//tag[position()<n]: Seleciona os elementos da tag especificada que estão em uma posição inferior a n.
//tag[position()>n]: Seleciona os elementos da tag especificada que estão em uma posição superior a n.
//tag[last()-n]: Seleciona o n-ésimo elemento a partir do último elemento da tag especificada.
//tag[@attr='valor']/text(): Seleciona o texto contido dentro do elemento com o atributo e valor especificados.
//tag[@attr='valor']/@atributo: Seleciona o valor do atributo específico dentro do elemento com o atributo e valor especificados.
//tag[starts-with(@attr, 'valor')]: Seleciona elementos com o atributo especificado que começa com o valor fornecido.
//tag[ends-with(@attr, 'valor')]: Seleciona elementos com o atributo especificado que termina com o valor fornecido.
//tag[contains(@attr, 'valor')]: Seleciona elementos com o atributo especificado que contém o valor fornecido.
//tag[not(@attr)]: Seleciona elementos da tag especificada que não possuem o atributo especificado.
//tag[@attr='valor1' or @attr='valor2']: Seleciona elementos com a tag especificada que possuem o atributo com um dos valores especificados.
//tag[@attr1='valor1' and not(@attr2)]: Seleciona elementos com a tag especificada que possuem o atributo1 com o valor1 e não possuem o atributo2.
//tag[position() mod n = 0]: Seleciona elementos da tag especificada em posições múltiplas de n.
//tag1/following-sibling::tag2: Seleciona elementos da tag2 que são irmãos seguintes da tag1.
//tag1/preceding-sibling::tag2: Seleciona elementos da tag2 que são irmãos anteriores da tag1.
//tag[@attr]/parent::parent::tag2: Seleciona elementos da tag2 que são avós do elemento com o atributo especificado.
//tag[descendant::tag2]: Seleciona elementos da tag especificada que possuem elementos descendentes da tag2.
//tag[ancestor::tag2]: Seleciona elementos da tag especificada que possuem elementos ancestrais da tag2.
//tag[position()=1]/self::tag: Seleciona o primeiro elemento da tag especificada, incluindo a si mesmo.
