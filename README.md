# Documentação

## CSS

### Básico

1) Extraindo texto de uma class
.escreva_a_class
 
2) Extraindo texto de um id
#escreva_o_ID
 
3) Extraindo texto de um tag
escreva_o_Tag
 
4) Extraindo Atributo do selector
Os atributos src e href são capturados automaticamente, para os demais utilizar:
escreva_o_selector “espaço” :attr(escreva o atributo)

5) Quando precisar extrair o texto de um código com src ou href utilizar:
escreva_o_selector “espaço” :text

### Filho mais proximo
"Filho" é o que está dentro da Tag.
A Tag é aberta com "<>" e fechada com "</>", exemplo <li></li>

7) Quando no comando de busca é utilizado o simbolo ">", com em `div > span > ul`, ele busca o filho que está ligado diretamente ao "Pai", ou seja ele vai procurar diretamente o ul, ligado ao spans ligado ao div.

8) Quando no comando de busca NÃO é utilizado o simbolo ">", com em `div span ul`, ele busca em tudo dentro do pai, ou seja ele vai procurar todos os ul que estejam dentro de qualquer span dentro do div, ou seja o span não precisa estar diretamente ligado ao Div, e o ul não necessáriamente ligado ao span.

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

  ### 



6) Extraindo texto de um vetor
.escreva_a_class:nth-child(escreva_o_vetor)
 
Extraindo atributos de um vetor
.escreva_a_class:nth-child(escreva_o_vetor) “espaço” :attr(escreva o atributo)
![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/a090586b-0793-41a7-9f95-65d230981904)
