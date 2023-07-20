# Erros de Paginação
## 1) Link Incompleto
O link na página principal está incompleto. Ex.: deveria estar www.zuk.com/leilão/001, porém está /leilão01.

Neste caso pode identificar o erro como: prefixo pendendete.

## 2) Java
Caso verifique na página principal que o problema não é o relatado anteriormente, ai devemos inserir o link da paginação no campo URL Teste, com o número da página se for o caso (não o {pagina}) clicar em atualizar e ver o preview, para ver se está puxando os links corretos.
   ![image](https://github.com/Apiraja/U.Move_Captacao/assets/137231287/d7498aa9-73df-453d-9f3f-63278ff8140e)

Caso os links não carreguem, ai pode colocar o erro como: Java

## 3) Tag dos Links
O Link dos lotes/leilões não estão dentro do tag `a`, erro: TAG dos Links

## 4) Paginação não numérica 
Paginação não é por número, se não carregar nada ai o erro é java, mas se carregar parcial, erro: paginação não numérica 

## 5) Redirecionamento leilão/lote
Vi um caso de redirecionamento, na página principal os links estão como .../detalhe_leilao/xxxx, e quando clica ele vai para .../detalhe_lote/xxxx

Neste caso apenas fiz o cadastro do leilão com a nomeclatura correta e do lote com a nomeclatura correta e funcionou, se não funcionar colocar erro: redirecionamento leilão/lote
