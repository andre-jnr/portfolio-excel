# Controle de notas fiscais

Vamos supor que estamos em uma unidade matriz, e somos do setor fiscal, temos que monitorar
todas as notas que são emitidas para todas as unidades.

Um controle de nota fiscal nos ajudar a:

- Ter um controle maior sobre as notas
- Detectar se todas as notas estão sendo lançadas
- Conferir se a compra é nossa
- Conferir se alguma nota cancelada será paga

### AVISO

- Todos os valores foram gerados pela fórmula `=aleatorio()*1000`, copiado e colado para
  que os valores permanecessem os mesmos.

# Como a planilha funciona

- É baixado um arquivo csv pelo site da sefaz, (nesse caso, eu simulei uma).
- Formatamos para uma tabela no excel.
- Baixamos um arquivo que contém as notas fiscais lançadas pelo ERP da empresa.
- Jogamos o arquivo do sistema numa aba nova
- deixamos uma coluna na tabela da sefaz para jogarmos a formula que vai conferir se todas da coluna `NF` vai está na coluna `NF` do sistema.
- A formula em questão é `=seerro(se(procv(valor_procurado;matriz;coluna;falso);"consta";"não consta");falso-erro)`

# Como o formula funciona

- `procv()`: procura o valor numa matriz.
- `se()`: verdadeiro -> se o `procv()` encontrar -> "consta".
- `se()`: falso -> se o `procv()` não encontrar -> "não consta"
- `seerro()`: garante que o `se()` vai funciona se o `procv()` der erro.
