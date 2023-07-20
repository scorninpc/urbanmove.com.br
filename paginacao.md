# Erros de Paginação
## 1) Prefixo pendendete
O link na página principal está incompleto. Ex.: deveria estar www.zuk.com/leilão/001, porém está /leilão01.


## 2) Java
Caso verifique na página principal que o problema não é o relatado anteriormente, ai devemos inserir o link da paginação no campo URL Teste, com o número da página se for o caso (não o {pagina}) clicar em atualizar e ver o preview, para ver se está puxando os links corretos.
   ![image](https://github.com/Apiraja/U.Move_Captacao/assets/137231287/d7498aa9-73df-453d-9f3f-63278ff8140e)


## 3) Tag dos Links
O Link dos lotes/leilões não estão dentro do tag `a`.

### Leiloeirolegentil   

//*[@class = 'Anuncio1_1']/@onclick = abrirDetalhesLeilao('20040810701730006050002');

Link = https://ssl1.visar.com.br/leiloeirolegentil.com.br/Leilao.asp?zz=20040810701730006050002

Solução, criar seletor para indicar onde estão os trechos de links, e algo tipo concat para criar o link válido.  

## 4) Paginação não numérica 
Paginação não é por número, se não carregar nada ai o erro é java, mas se carregar parcial.

## 5) Redirecionamento leilão/lote
Vi um caso de redirecionamento, na página principal os links estão como .../detalhe_leilao/xxxx, e quando clica ele vai para .../detalhe_lote/xxxx

### Marquesleiloes
Link na "home" <a href="https://www.marquesleiloes.com.br/leilao/detalhe_leilao/207#conteudo">+ Detalhes</a>
Quando clicado se torna https://www.marquesleiloes.com.br/leilao/detalhe_lote/207/#conteudo

Solução quando buscado o link detalhe_leilao ele será redirecionado, pegar o link redirecionado e verificar se está dentro do padrão de lote.

Podemos selecionar que esta opção é necessária.

## 6) Duas páginas de leilão e depois a do lote
Exceção da exceção, desconsiderar por hora

