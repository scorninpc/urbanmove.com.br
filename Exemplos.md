# Exemplos xPath

## Básico

### ID
//*[@id= 'Leilão'] 

### Classe

//*[@class = 'Leilão'] 

### Contém Palavra

//span[contains(text(),'Leilão')] 



//span[contains(text(),'Leilão')]/following-sibling::spam 

(Retorna o irmão que é um spam)

//span[contains(text(),'Leilão')]/following-sibling::text() 

(Retorna o irmão que é um texto)


## Texto

substring-after(//*[@id= 'Leilão'], 'R$')

substring-before(//*[@id= 'Leilão'], 'R$')

substring-before(substring-after(//*[@id= 'Leilão'], 'R$'), 'R$')

normalize-space(//*[@id= 'Leilão'])

## Outros

//*[@id= 'Leilão']/.. (Pai)

//*[@id= 'Leilão']/div (Filho direto)

//*[@id= 'Leilão']/div (Filho)

//*[@id= 'Leilão'][2] (Vetor)

//*[@id= 'Leilão']/@src (Atributo)

//*[@id= 'Leilão'][2]/..//img/@src
