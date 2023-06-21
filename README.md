# Documentação

## CSS

### Básico

1) Extraindo texto de uma class: `.escreva_a_class`

2) Extraindo texto de um id: `#escreva_o_ID`
 
3) Extraindo texto de um tag: `escreva_o_Tag`
 
4) Extraindo Atributo do selector
    Os atributos src e href são capturados automaticamente, para os demais utilizar:
    `escreva_o_selector “espaço” :attr(escreva o atributo)`

5) Quando precisar extrair o texto de um código com src ou href utilizar:
    `escreva_o_selector “espaço” :text`

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

- O seletor `div ul` vai retornar as 2 `UL`.
- O seletor `div > ul` só vai pegar o `UL` que é filho direto da `DIV`. 
- O seletor `div > span > ul` vai pegar o `UL` de dentro do `SPAN`, porque o `UL` é filho direto do `SPAN`, que é filho direto do `DIV`

  ### Vetores
  Quando existir mais de um resultado para a busca, deve ser indicado qual o item que se deseja bucar, o 1º, 2º...
  Para isso deve ser utilizado o `:nth-child(escreva_a_posição)` após a `classe`, `id`, `tag` desejado, como abaixo

9) Extraindo texto de um vetor
    `.escreva_a_class:nth-child(escreva_a_posição)`
 
10) Extraindo atributos de um vetor
    `.escreva_a_class:nth-child(escreva_a_posição) “espaço” :attr(escreva o atributo)`

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

O seletor `div ul` vai retornar as 3 `UL`.
- O seletor `div ul.:nth-child(1)` vai retornar a primeira `UL`
- O seletor `div ul.:nth-child(2)` vai retornar a segunda `UL`

O seletor `div > ul` só vai pegar as duas `UL` que são filhos direto da `DIV`.
- Neste caso o seletor `div > ul.:nth-child(1)` vai retornar a segunda `UL`
- E o seletor `div > ul:nth-child(2)` vai retornar a terceira `UL`

O seletor `div a` vai pegar as seis `A` que estão dentro da `DIV`.
O seletor `div ul a` continua pegando as seis `A` que estão dentro das `UL` `DIV`.

11) No exemplo acima se atentar ao caso:
    O seletor `div ul a:nth-child(3)` não pegará o terceiro `A`, os `A` que estão dentro das `UL` que não possuem 3 `A` são ignorados,      nesse caso só será retornado o terceiro `A`das `UL` com 3 `A`, nesse caso, apenas a terceira `UL` possui 3 `A`, então será              retornado o último `A`.

 ### Utilizando o Parenting

 ### Utilizando o Find

### Busca de Texto na Página
Em muitos sites os seletores não são utilizados para indexar a informação, mas apenas a formatação como no exemplo:

```html
<div x-data="{ open: true }" class="mx-2 mt-4 grow-0 rounded-md bg-white p-2 shadow-sm shadow-zinc-200 dark:bg-zinc-800 dark:shadow-zinc-900 md:mx-0">
<div @click="open = !open" class="my-3 mt-3 flex cursor-pointer border-b-[1px] px-2 py-2 font-bold uppercase text-zinc-600 dark:border-zinc-700 dark:text-zinc-400">
<div>
<i class="fa-solid fa-circle-question animate-pulse"></i> INFORMAÇÕES IMPORTANTES
</div>
<div class="flex-1 text-right">
<i class="fa-solid fa-square-minus" :class="open ? 'fa-square-minus' : 'fa-square-plus'"></i>
</div>
</div>
<div x-show="open" class="py-2 px-1 text-zinc-700 dark:bg-transparent dark:text-zinc-400">
<div class="prose max-w-none dark:prose-dark">
<div>
<div style="text-align: justify;">NO PRIMEIRO LEILÃO OS BENS SERÃO OFERECIDOS SOMENTE PELO VALOR DE AVALIAÇÃO E NO SEGUNDO LEILÃO, OFERECIDOS PELO LANCE MÍNIMO (art. 891 NCPC)<br><br></div>
<div style="text-align: justify;"><span style="color: #169179;">A REALIZAÇÃO DO LEILÃO PRESENCIAL, ESTÁ CONDICIONADA AO RETORNO DA PERMISSÃO DE AGLOMERAÇÕES DE PESSOAS, CASO AS AUTORIDADES NÃO ESTEJAM PERMITINDO ESSAS AGLOMERAÇÕES NOS DIAS DOS LEILÕES, OS MESMOS SERÃO REALIZADOS APENAS NA MODALIDADE ELETRÔNICA (ONLINE)</span><br><br></div>
<div style="text-align: justify;">LEILÕES ELETRÔNICOS DEVEM SER ACOMPANHADOS ATRAVÉS DO AUDITÓRIO DE LEILÃO. Leilão Eletrônico, conforme Artigo 879, II do CPC/2015. PARA PARTICIPAÇÃO E OFERTA DE LANCES ELETRÔNICOS, OS INTERESSADOS DEVERÃO FAZER CADASTRO PRÉVIO NO SITE&nbsp;<a href="https://amleiloeiro.com.br/cadastre">https://amleiloeiro.com.br/cadastre</a>&nbsp;ORIENTAMOS REALIZAR O CADASTRO E O ENVIO DA DOCUMENTAÇÃO NECESSÁRIA E SOLICITAR HABILITAÇÃO&nbsp;EM ATÉ 24 HORAS ANTES DO LEILÃO, EVITANDO ASSIM, PROBLEMAS NA LIBERAÇÃO DE SUA PARTICIPAÇÃO.<br><br></div>
<div style="text-align: justify;"><span style="color: #169179;">MEDIANTE ENTRADA DE 25%, OS IMÓVEIS PODERÃO SER PARCELADO EM ATÉ 30 VEZES. (art. 895, §1º do NCPC) - CONSULTE O EDITAL DE LEILÃO<br><br></span></div>
<div style="text-align: justify;">ATENÇÃO! NÃO DEIXE PARA DAR SEU LANCE NOS ÚLTIMOS SEGUNDOS PARA O ENCERRAMENTO DO CRONÔMETRO REGRESSIVO, POIS DEPENDENDO DA INTERNET DO USUÁRIO E DO TRÁFEGO DE SINAL NAQUELE MOMENTO, O LANCE PODERÁ NÃO SER COMPUTADO. ISSO PODERÁ OCORRER DEVIDO AO DELAY (ATRASO) DE TRANSMISSÃO, EXISTENTE EM TODOS OS MEIOS DE COMUNICAÇÃO POR SINAL.<br><br></div>
<div style="text-align: justify;"><span style="color: #169179;">LANCES À VISTA TERÃO PREFERÊNCIA, BASTANDO IGUALAR AO VALOR DO ÚLTIMO LANCE PARCELADO OFERTADO, O QUE NÃO INTERFERE NA CONTINUIDADE DA DISPUTA. O LANCE A PRAZO TEM DE SUPERAR O LANCE ANTERIOR, JÁ O LANCE À VISTA BASTA IGUALAR O ÚLTIMO LANCE A PRAZO E TERÁ PREFERÊNCIA.</span><br><br></div>
<div style="text-align: justify;">CASO HAJA DIVERGÊNCIA ENTRE A FOTO E O BEM PENHORADO OU APREENDIDO NOS AUTOS, TERÁ VALIDADE O ITEM DESCRITO NO TERMO DE PENHORA OU APREENSÃO CONSTANTE NO PROCESSO.</div>
</div>
</div>
</div>
</div>
```
Neste caso acima, a class dos elementos sempre fazem referência a formatação e não devem ser utilizadas, por inúmeros motivos.
Olhando a página, dá pra perceber que se trata de um "bloco" 

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/bbc5860a-1f4c-486e-831f-eb96112889d4)

Composto por um cabeçalho

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/b469ee10-6b6b-4f71-9510-9de107debe78)

E um texto 

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/e9489b61-02ec-4d05-a887-ad41d9eb1342)

Como não temos referências para ancorar nossa busca, podemos utilizar o recurso `contains`.
Ele busca um trecho de texto dentro do código e ancora nossa busca a este seletor.
A sintaxe deve ser `tag:contains('Palavra buscada')

Exemplo:






