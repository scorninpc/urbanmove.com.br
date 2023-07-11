# Casos

# 11/07

## Nomeclatura de leiloeiros aleatórios
Quando o leiloeiro não possuir lotes, ou lotes alheios (gado, etc): Z_SL_Nome_do Leiloeiro

# 10/07

## Nunca utilizar data de abertura, sempre encerramento

...Sempre encerramento

Quando o código para data de leilão único, é o mesmo da primeira praça, não precisa preencher leilão único

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/58e9dddf-f5f0-4fbe-ad0e-e174372084cd)

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/5c1eca76-5f57-4f28-8f91-922f4065d53f)


## Informação de último lance
Essa informação de último lance é muito importante, podem pegar mesmo que seja um texto indicando que não houve lance.

Depois quando tivermos tudo rodando podemos achar imóveis que tiveram lances e melhorar o seletor.

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/e193259c-5995-4426-a96a-232e76f020f7)

## Endereço na descrição 
Neste caso abaixo, onde o endereço não aparece em nenhum campo específico, mas está na descrição. É interessante usar o campo da descrição, ou parágrafos específicos como endereço. Normalmente o google maps retorna alguma coisa bem próxima do endereço específico. Ou trataremos no back depois.

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/24f6a049-cf4b-4c16-9021-d66bb977fe1f)

## Endereço em campos 

Neste caso abaixo se pegarmos apenas o nome da rua, o maps não irá identificar, pois esta rua existe em vários municípios, precisamos de mais informação.

O ideal seria pegar de cidade para frente. 

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/829752a0-0591-4b51-b4c4-692127bc567f)


## Data e Preço se alteram com a data do leilão
A informação que está como text passa a ser <s>, quando vencida a data do primeiro leilão.

Neste caso podemos pegar o pai e usar substring para pegar o que vem depois de R$

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/90a48e53-462f-44b8-9c86-b24f433c80c9)
