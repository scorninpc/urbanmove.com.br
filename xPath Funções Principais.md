# xPath - Funções Principais 

### Básico

//*[@id= 'Leilão'] 

//*[@class = 'Leilão'] 

//span[contains(text(),'Leilão')] 

#### Pesquisa o texto no nome das classes

//*[contains(@class,'Leilão')]

#### Retorna o irmão

//span[contains(text(),'Leilão')]/following-sibling::text()

//span[contains(text(),'Leilão')]/preceding-sibling::spam[3]

### Texto

substring-after(//*[@id= 'Leilão'], 'R$')

substring-before(//*[@id= 'Leilão'], 'R$')

substring-before(substring-after(//*[@id= 'Leilão'], 'R$'), 'R$')

normalize-space(//*[@id= 'Leilão'])

### Outros

Pai: /*[@id= 'Leilão']/.. 

Filho direto: //*[@id= 'Leilão']/div 

Filho: /*[@id= 'Leilão']//div 

Vetor: //*[@id= 'Leilão'][2] 

Atributo: //*[@id= 'Leilão']/@src

Retorna o 3º Elemento span encontrado dentro de uma class chamada Leilão: (//*[@class = 'Leilão'] //span)[3]

Retorna os spans que estão em 3º lugar dentro das class que se chamam Leilão: //*[@class = 'Leilão'] //span[3]

//*[@id= 'Leilão'][2]/..//img/@src

//*[@id= 'Leilão'][2]/..//img/span[contains(text(),'Leilão')]
