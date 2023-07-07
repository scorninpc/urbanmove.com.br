# Documentação

## Tutoriais

Cadastro de sites: https://youtu.be/q2n6GNkcuLE

Introdução xPath: https://youtu.be/hB1BdqHLXT0

Exemplo 01 Zuk: https://youtu.be/INwSHZwfIjc

Exemplo 02 Biasi: https://youtu.be/GkxmZVA7mvA

Exemplo 03 Brame: https://youtu.be/s_E3Vas3WjE


## Pontos importantes para efetuar o cadastro

### Nomeclatura Painel:
Novo site: A_Seu_nome_Nome_do Leiloeiro

Quando revisado o nome será alterado para: R_Seu_nome_Nome_do Leiloeiro

Quando validado no banco de dados: Nome_do_Leiloeiro

Quando houver problemas que restrinjam o cadastro: Z_Hold_Nome_do Leiloeiro

### Controle lista de sites

(Atualização) Criada a Lista de Sites 02, quando pegar um lote, pode escrever o nome dele em cima dos links com seu nome na frente

Preenchimento finalizado: - ok

Preenchimento com pendência: - Pendente "especificação do campo, ou do problema"

Erro: - Erro "especificação do erro" (em branco, cloudflare, falha no servidor.... seguir o padrão que já está)

### Outros erros

Caso seja identificado um erro de funcionamento que afete vários sites, abrir um issue no github especificando e dando links e nomes para melhor resolver

## Erros no preview

Quando clicar no preview do link que está testando (olho ao lado do link) e der erro no retorno da página, testar se as variáveis realmente não estão funcionando, neste caso, colocar o hold no nome do site e relatar erro na lista de controle.

## Ajax

Sempre que abrir o primeiro link de leiloeiro para testar, desabilitar o  javascript clicando nas configurações do console do navegaor (engrenagem a direita, ai lá no final... pelo menos no chrome) e atualizar a página.

Caso alguma informação não seja mostrada, é necessário alterar o cadastro do leiloeiro para Tipo de Paginação: AJAX e Delay para 2, ou testar delay maior caso ache necessário

![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/b13358d5-7531-47d7-8d2b-658f06099586)


![image](https://github.com/scorninpc/urbanmove.com.br/assets/137231287/39fcc1ea-29a7-4f6a-b0fb-866bf3f32bb2)


