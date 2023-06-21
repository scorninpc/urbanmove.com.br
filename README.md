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

7) Quando no comando de busca é utilizado o simbolo `>`, com em `div > span > ul`, ele busca o filho que está ligado diretamente ao "Pai", ou seja ele vai procurar diretamente o `ul`, ligado ao `span` ligado ao `div`.

8) Quando no comando de busca NÃO é utilizado o simbolo `>`, com em `div span ul`, ele busca em tudo dentro do pai, ou seja ele vai procurar todos os `ul` que estejam dentro de qualquer `span` dentro do `div`, ou seja o `span` não precisa estar diretamente ligado ao `div`, e o `ul` não necessáriamente ligado ao `span`.

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
O seletor `div ul a:nth-child(3)` não pegará o terceiro `A`, os `A` que estão dentro das `UL` que não possuem 3 `A` são ignorados, nesse caso só será retornado o terceiro `A`das `UL` com 3 `A`, nesse caso, apenas a terceira `UL` possui 3 `A`, então será retornado o último `A`.

 ### Busca de Texto na Página

 ### Utilizando o Parenting

 ### Utilizando o Find

