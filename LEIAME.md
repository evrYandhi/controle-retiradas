# Controle de retiradas do dono

Ferramenta do Capítulo 1 do e-book. Ajuda os sócios de um negócio pequeno a anotar o dinheiro que tiram da empresa para uso pessoal e a comparar esse total com a sobra da empresa no mês.

O site inteiro é um arquivo só: **index.html**. Não precisa instalar nada e funciona sem internet depois de aberto.

Endereço publicado: https://evryandhi.github.io/controle-retiradas/

**Não mude o nome do arquivo `index.html` nem o nome do repositório ou da conta no GitHub.** O link e o QR code estão impressos no e-book, e os dados de quem usa o site ficam presos a esse endereço.

---

## 1. O que o site faz

**Tela Retiradas.** Cada retirada tem data, para que foi, quem retirou e valor. A lista mostra o total acumulado do mês depois de cada retirada. Quando o acumulado chega ao pró-labore combinado, aparece o aviso "As retiradas do mês chegaram ao pró-labore combinado."

**Tela Mês.**
- Receita do mês: quanto a empresa vendeu no mês.
- Gastos da empresa sem o pró-labore: mercadoria, aluguel, equipe, impostos e as demais contas do negócio.
- Pró-labore combinado: o valor fixo mensal dos sócios. No 1º mês, fica em branco. Do 2º mês em diante, já vem preenchido com o valor do mês anterior, e a pessoa pode trocar.
- Dinheiro da casa colocado na empresa (se houver): só fica registrado e aparece no resumo. Não entra nos cálculos.

**Tela Resultado.**
- Sobra da empresa = receita do mês menos gastos sem o pró-labore.
- Total retirado = soma das retiradas do mês.
- Parte da sobra usada pela casa = total retirado dividido pela sobra, com 1 casa decimal (ex.: 98,2%).
- Ficou na empresa = sobra menos total retirado.
- Faixa do mês:
  - **Faixa A:** total retirado até o pró-labore combinado e até 100,0% da sobra. Decisão: "Mantenha o valor e o dia do pró-labore."
  - **Faixa B:** total retirado acima do combinado, mas até 100,0% da sobra. Decisão: "Volte ao valor combinado no mês seguinte e anote o motivo de cada retirada extra."
  - **Faixa C:** total retirado acima de 100,0% da sobra. Decisão: "Reduza o pró-labore até caber na sobra e consulte os Capítulos 4 e 5."
- Sem pró-labore combinado (1º mês), aparece só "Até 100,0%, as retiradas couberam na sobra." ou "Acima de 100,0%, a casa usou dinheiro que a empresa não deixou.", seguida de "Use esses números para fixar o pró-labore em um valor que caiba na sobra."
- O resumo do mês mostra também o total retirado por sócio. Retiradas feitas pelos sócios juntos aparecem numa linha separada, sem divisão.

**Casos de limite.**
- A faixa é decidida pelos valores exatos em reais. Se o total passar da sobra por poucos centavos ou reais, o arredondamento daria "100,0%". Nesse caso o site escreve "acima de 100,0%" e mostra a faixa C. Exatamente igual à sobra conta como 100,0% (faixa A ou B).
- Se a empresa não teve sobra (gastos iguais ou maiores que a receita), o percentual aparece como "Não dá para calcular" e qualquer retirada fica na faixa C.

**Tela Histórico.** Tabela com a sobra e o total retirado de cada mês, lado a lado, gráfico mês a mês e média da sobra.

---

## 2. Como abrir o site

**No computador:** baixe o `index.html` e dê dois cliques nele.

**No celular:** abra o link publicado no navegador.

**Atenção:** os dados que uma pessoa digita ficam no navegador, ligados ao endereço por onde ela abriu o site. Se você testar abrindo o arquivo no computador e depois abrir o link publicado, vai ver duas listas diferentes. Isso é normal.

---

## 3. Nomes dos sócios

Cada leitor escreve os nomes dos sócios do próprio negócio dentro do site: botão **Menu**, depois **Nomes dos sócios**. O mesmo botão aparece em "Quem retirou?" e na tela Meus dados. Cabem até 4 nomes, que valem para todos os meses. Com 2 ou mais sócios, aparece também a opção com todos juntos (ex.: "Jonas e Camila").

Os nomes do exemplo (Jonas e Camila) ficam no bloco do exemplo, explicado abaixo.

---

## 4. Como trocar os dados do exemplo

Os dados do botão "Ver um exemplo" ficam no começo do arquivo `index.html`, no bloco que começa com:

```
2) DADOS DO EXEMPLO
```

Ele fica perto da linha 48 e hoje traz o caso Brasa no Bairro, mês 3:

```
var EXEMPLO = {
  nomeDoMes: "Mês 3",
  socios: ["Jonas", "Camila"],
  receita: "41.990",
  gastos: "35.883",
  proLabore: "6.000",
  dinheiroDaCasa: "",
  retiradas: [
    ["5", "Pró-labore dos 2 sócios", "Jonas e Camila", "6.000"]
  ]
};
```

Resultado esperado: sobra R$ 6.107, total retirado R$ 6.000, parte da sobra 98,2%, ficou na empresa R$ 107, faixa A.

Regras para não quebrar o site:

- Troque só o que está **entre aspas**.
- `nomeDoMes` é como o mês aparece no topo durante o exemplo.
- Valores podem ser escritos como no dia a dia: `"1200"`, `"1.200"` ou `"1.200,50"`.
- Sem pró-labore ou sem dinheiro da casa: deixe as aspas vazias, `""`.
- Cada retirada é uma linha `["dia", "para que foi", "quem retirou", "valor"],`.
- "Quem retirou" precisa ser um dos nomes de `socios` ou todos juntos, escritos como o site escreve: com 2 sócios, `"Jonas e Camila"`; com 3, `"Ana, Bia e Caio"`.
- **Toda linha de retirada termina com vírgula, menos a última.**

Depois de salvar, abra o site, toque em **Menu** e depois em **Ver um exemplo** para conferir.

---

## 5. Como mudar cores, fonte e textos

### Nome do e-book, cores e fonte

Ficam no bloco **1) PERSONALIZAÇÃO**, no começo do arquivo (perto da linha 11).

- **Nome do e-book:** linha 17. Hoje está `"E-book de Gestão Financeira"`, que é um nome provisório. Troque pelo nome verdadeiro.
- **Cores:** cada cor é um código que começa com `#` seguido de 6 letras ou números. Ao lado de cada uma há um comentário dizendo onde ela aparece. O verde (`coube`) é a faixa A, o amarelo-escuro (`atencao`) é a faixa B e o vermelho (`passou`) é a faixa C. Mantenha essas cores escuras o bastante para ler sobre o fundo clarinho delas.
- **Botões rápidos de motivo:** lista `motivosRapidos`. Mantenha "Outro" no final.

### Textos das faixas e outros textos

- As frases das faixas A, B e C ficam no bloco `var FAIXAS` (perto da linha 749). Elas estão iguais ao Capítulo 1. Se o capítulo mudar, mude aqui também.
- O passo a passo das 3 telas fica em `var PASSOS`, e o texto "O que conta como retirada" fica em `var EXPLICA_RETIRADA`, logo abaixo.
- Para outras frases, use a busca (Ctrl+F no Windows, Cmd+F no Mac), digite um pedaço da frase e troque só as palavras, sem apagar aspas, sinais `<` `>` ou o que estiver em volta.

**Não mude** a linha `var CHAVE = "controleRetiradasDono.v1";` (perto da linha 744). Ela é o nome da gaveta onde os dados de cada pessoa ficam guardados. Se mudar, quem já usa o site vai abrir a ferramenta vazia.

### Como abrir o arquivo para editar

- **Mais fácil, pelo GitHub:** abra o `index.html` na página do repositório e clique no ícone de lápis ("Edit this file"). Edite, clique em **Commit changes...** e confirme em **Commit changes**. O site atualiza sozinho em 1 ou 2 minutos.
- **No Windows:** botão direito em `index.html`, **Abrir com**, **Bloco de Notas**. Salve com Ctrl+S.
- **No Mac:** o TextEdit pode estragar o arquivo. Prefira editar pelo GitHub.

Depois de qualquer mudança, abra o site e confira. Se a tela ficar em branco, quase sempre faltou uma aspa ou uma vírgula. Desfaça a última mudança.

---

## 6. Dados de quem já usava o site

A versão anterior guardava os campos com outros nomes ("quanto entrou", "quanto a empresa gastou" e "retirada fixa"). Ao abrir a versão nova, o site converte esses dados sozinho para "receita do mês", "gastos da empresa sem o pró-labore" e "pró-labore combinado", sem apagar nada. Cópias de segurança feitas na versão anterior também são aceitas e convertidas.

As retiradas antigas não tinham "quem retirou". Elas aparecem como "Não informado" até a pessoa corrigir cada uma.

---

## 7. Como atualizar o site publicado

1. Entre em github.com e abra o repositório `controle-retiradas`.
2. Clique em **Add file** e depois em **Upload files**.
3. Arraste o `index.html` novo (e o `LEIAME.md`, se mudou).
4. Clique em **Commit changes**.
5. Espere 1 ou 2 minutos e abra o link do site. Se ainda aparecer a versão antiga, recarregue a página.

O arquivo enviado substitui o que está lá, porque tem o mesmo nome. O endereço não muda.

---

## 8. O que a ferramenta guarda e onde

- Tudo fica no navegador do aparelho da pessoa. Não há cadastro nem servidor, e nada é enviado para a internet.
- Se a pessoa limpar o navegador, os dados somem. Por isso existe o botão "Fazer cópia de segurança".
- No iPhone, o Safari pode apagar os dados de sites que ficam muitos dias sem uso. O site mostra uma dica para adicionar a ferramenta à tela de início.

## 9. Testes

A pasta `testes` tem as fotos das telas e o relatório dos testes automáticos (`resultados.json`). Ela não precisa ir para o GitHub.
