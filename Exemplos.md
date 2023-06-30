# Exemplos xPath

## Básico
//*[@id= 'Leilão']

//*[@class = 'Leilão']

//span[contains(text(),'Leilão')]

//span[contains(text(),'Leilão')]/following-sibling::span

//span[contains(text(),'Leilão')]/following-sibling::text()


## Texto

substring-after(//*[@id= 'Leilão'], 'R$')

substring-before(//*[@id= 'Leilão'], 'R$')

substring-before(substring-after(//*[@id= 'Leilão'], 'R$'), 'R$')

## Outros

//*[@id= 'Leilão']/..

//*[@id= 'Leilão'][2]

//*[@id= 'Leilão'][2]/..//img/@alt
