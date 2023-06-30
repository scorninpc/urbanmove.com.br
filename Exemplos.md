# Exemplos xPath

### Básico

//*[@id= 'Leilão'] 

//*[@class = 'Leilão'] 

//span[contains(text(),'Leilão')] 

#### Pesquisa o texto no nome das classes

//*[contains(@class,'Leilão')]

#### Retorna o irmão que é um spam

//span[contains(text(),'Leilão')]/following-sibling::spam 

//span[contains(text(),'Leilão')]/following-sibling::text() 

### Texto

substring-after(//*[@id= 'Leilão'], 'R$')

substring-before(//*[@id= 'Leilão'], 'R$')

substring-before(substring-after(//*[@id= 'Leilão'], 'R$'), 'R$')

normalize-space(//*[@id= 'Leilão'])

### Outros

#### Pai

//*[@id= 'Leilão']/.. 

#### Filho direto

//*[@id= 'Leilão']/div 

#### Filho

//*[@id= 'Leilão']/div 

#### Vetor

//*[@id= 'Leilão'][2] 

#### Atributo

//*[@id= 'Leilão']/@src

//*[@id= 'Leilão'][2]/..//img/@src


