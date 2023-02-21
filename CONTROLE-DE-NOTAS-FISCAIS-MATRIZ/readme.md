# Controle de notas fiscais

![image](https://user-images.githubusercontent.com/99357762/220482281-a22ea4f0-0a5a-434f-9278-9afe26e5ae09.png)

Vamos supor que estamos em uma unidade matriz, e somos do setor fiscal, temos que monitorar
todas as notas que são emitidas para todas as unidades.

Um controle de nota fiscal nos ajudar a:

- Ter um controle maior sobre as notas.
- Detectar se todas as notas estão sendo lançadas.
- Conferir se a compra é nossa.
- Conferir se alguma nota cancelada será paga.

### AVISO

- Todos os valores foram gerados pela fórmula `=aleatorio()*1000`, copiado e colado para
  que os valores permanecessem os mesmos.
  
# Como navegar pela planilha

Na tela inicial, Na parte inferior temos um resumo sobre as notas fiscais (lembrando que é tudo aleatório, então os números não batem).

![image](https://user-images.githubusercontent.com/99357762/220482595-f811b706-daa0-4d16-be2e-bae6be3d66c8.png)

Em cima temos os botôes que levam para cada guia da planilha.

![image](https://user-images.githubusercontent.com/99357762/220482723-5628157d-31b0-4667-ba3b-b30a8a5469d0.png)

- Nos botões de `controle de notas`, somos levados aos relatórios com base nos arquivos csv da sefaz.
- Nos botôes `base de dados`, somos levados as informações baixadas no sistema.

## Relatórios

Dentro de cada relatório, podemos ver um resumo com todas as informações necessárias para analise.

![image](https://user-images.githubusercontent.com/99357762/220483315-f918f394-a807-4510-82b9-65a9401b2061.png)

- As linhas verdes são as notas lançadas no sistema.
- As linhas vermelhas são as que não constam no sistema.

Nos botões de cima, podemos ir conferir se a nota realmente não consta no sistema, basta clica em `sistema`.

![image](https://user-images.githubusercontent.com/99357762/220483585-9e89bc92-e2f5-473b-8612-35d9de2b6034.png)

Digite no filtro a nota que estamos procurando.

![image](https://user-images.githubusercontent.com/99357762/220483705-29e1ac28-217e-486a-9679-d9f1b31ce60d.png)

# Como a planilha funciona

- É baixado um arquivo csv pelo site da sefaz, (nesse caso, eu simulei uma).
- Formatamos para uma tabela no excel.
- Baixamos um arquivo que contém as notas fiscais lançadas pelo ERP da empresa.
- Jogamos o arquivo do sistema numa aba nova.
- deixamos uma coluna na tabela da sefaz para jogarmos a formula que vai conferir se todas da coluna `NF` vai está na coluna `NF` do sistema.
- A formula em questão é `=seerro(se(procv(valor_procurado;matriz;coluna;falso);"consta";"não consta");"não consta")`.

# Como o formula funciona

- `procv()`: procura o valor na coluna indicada, numa matriz.
- `se()`: verdadeiro -> se o `procv()` encontrar o valor -> "consta".
- `se()`: falso -> se o `procv()` não encontrar o valor -> "não consta"
- `seerro()`: garante que o `se()` vai funciona se o `procv()` der erro.
