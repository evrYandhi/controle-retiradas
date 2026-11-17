# Controle de retiradas do dono

Ferramenta do Capítulo 1 do e-book. Ajuda os sócios de um negócio pequeno a anotar o dinheiro que tiram da empresa para uso pessoal e a comparar esse total com a sobra da empresa no mês.

O site tem dois arquivos: **index.html** (Controle de retiradas, Capítulo 1) e **quadro.html** (Quadro dos 4 indicadores, Conclusão). Cada um funciona sozinho, não precisa instalar nada e funciona sem internet depois de aberto.

Endereço publicado: https://evryandhi.github.io/controle-retiradas/

Página da Conclusão (Quadro dos 4 indicadores): https://evryandhi.github.io/controle-retiradas/quadro.html (veja a seção 10).

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
3. Arraste os arquivos que mudaram (`index.html`, `quadro.html` e `LEIAME.md`). Os dois arquivos do site precisam ficar na mesma pasta do repositório, a principal.
4. Clique em **Commit changes**.
5. Espere 1 ou 2 minutos e abra o link do site. Se ainda aparecer a versão antiga, recarregue a página.

O arquivo enviado substitui o que está lá, porque tem o mesmo nome. O endereço não muda.

---

## 8. O que a ferramenta guarda e onde

- Tudo fica no navegador do aparelho da pessoa. Não há cadastro nem servidor, e nada é enviado para a internet.
- Se a pessoa limpar o navegador, os dados somem. Por isso existe o botão "Fazer cópia de segurança".
- No iPhone, o Safari pode apagar os dados de sites que ficam muitos dias sem uso. O site mostra uma dica para adicionar a ferramenta à tela de início.

## 9. Testes

As pastas `testes` (Controle de retiradas) e `testes-quadro` (Quadro dos 4 indicadores) têm as fotos das telas e o relatório dos testes automáticos (`resultados.json`). Elas não precisam ir para o GitHub.

---

## 10. Página nova: Quadro dos 4 indicadores (Conclusão)

Arquivo: **quadro.html**, na mesma pasta do `index.html`.

Endereço: https://evryandhi.github.io/controle-retiradas/quadro.html

O `index.html` tem um link para ela no rodapé ("Quadro dos 4 indicadores (Conclusão)"), e ela tem um link de volta no topo ("Controle de retiradas (Capítulo 1)").

### O que a página faz

A página tem 5 abas na barra de baixo.

**Semana (quadro da semana, toda segunda-feira).** A pessoa informa a data e 7 valores: caixa, contas a receber, estoque, fornecedores, salários e encargos, impostos e parcelas de empréstimo. Depois informa o total de saídas do mês. O resultado aparece no alto da tela:
- **Saldo disponível**, em destaque: capital circulante líquido menos necessidade de capital de giro (o mesmo que caixa menos parcelas).
- **Faixa de decisão**, logo abaixo:
  - Faixa 1: saldo disponível abaixo de R$ 0.
  - Faixa 2: saldo de R$ 0 até abaixo de 7 dias de desembolso. Saldo exatamente R$ 0 é faixa 2.
  - Faixa 3: saldo igual ou acima de 7 dias de desembolso.
  - Nas faixas 1 e 2 aparecem também a meta da faixa 3 (7 × desembolso diário) e quanto falta para chegar nela.
- **Capital circulante líquido** = (1 + 2 + 3) − (4 + 5 + 6 + 7).
- **Necessidade de capital de giro** = (2 + 3) − (4 + 5 + 6).
- **Quanto da folga o giro consome** = necessidade de capital de giro ÷ capital circulante líquido. Se o capital circulante líquido for zero ou negativo, aparece "Sem folga: o capital circulante líquido não é positivo".
- **Desembolso diário** = total de saídas do mês ÷ 30, arredondado para reais inteiros antes das outras contas.
- **Fôlego de caixa livre** = saldo disponível ÷ desembolso diário, em dias.
- **Fôlego de caixa** = caixa ÷ desembolso diário, em dias, em letra menor.

Se a pessoa usa o Controle de retiradas no mesmo aparelho, o total de saídas de um quadro novo já vem com a soma "gastos da empresa sem o pró-labore + pró-labore combinado" do último mês que tem os dois valores preenchidos. A pessoa pode trocar. Se faltar o pró-labore nesse mês, o site não sugere nada.

Quando há um quadro anterior, a tela compara o saldo disponível ("subiu R$ X" ou "caiu R$ X"). Se caiu, mostra qual destas linhas mudou mais em reais: contas a receber, estoque, fornecedores, salários e encargos ou impostos.

**Mês (no último dia do mês).** A pessoa informa:
- custo da mercadoria do mês;
- receita do mês;
- receita do mês que entra a prazo (cartão e plataforma);
- em quantos dias o cartão e a plataforma pagam.

O estoque e os fornecedores vêm do último quadro semanal com data dentro do mês. Se o mês não tiver quadro, vêm do quadro feito nos 7 primeiros dias do mês seguinte, que mostra como o mês terminou. A pessoa pode trocar.

O site calcula, em dias:
- prazo de estoque;
- prazo de recebimento;
- prazo de pagamento;
- ciclo financeiro = prazo de estoque + prazo de recebimento − prazo de pagamento.

O ciclo financeiro soma os prazos já arredondados que aparecem na tela, para a conta do leitor sempre bater. Sem estoque, o prazo de estoque é 0 dias. Venda só à vista (receita a prazo igual a 0), o prazo de recebimento é 0 dias.

**Teste.** São 10 perguntas de sim ou não, uma por capítulo. O resultado só aparece com as 10 respondidas:
- 0 a 3 sim: "O livro ainda não virou rotina na empresa."
- 4 a 7 sim: "Parte das práticas existe, com lacunas."
- 8 a 10 sim: "A base existe e funciona."

O site também lista os capítulos para reler (os de cada "não") e compara com o teste anterior. Cada teste fica guardado com a data. Se a pessoa refizer o teste no mesmo dia, o novo substitui o daquele dia.

**Plano.** São 4 semanas. Cada uma tem:
- número da semana, numa lista de indicadores, que começa em "Saldo disponível";
- valor na segunda-feira, que vem sozinho do quadro feito naquela semana;
- ação da semana, com sugestões para tocar e preencher;
- capítulo de apoio;
- marcação "Feito".

A semana 1 começa na data de "Começo do plano". Depois de 4 semanas (28 dias) aparece "Refaça o teste do livro e monte o plano dos próximos 30 dias." O botão "Começar um plano novo" guarda o plano atual na lista de planos anteriores.

**Histórico.** Mostra:
- os quadros semanais por data, com saldo disponível, fôlego de caixa livre e faixa;
- as partes do mês guardadas, com o ciclo financeiro;
- os testes do livro.

### Formatos

- Resultados em reais sem centavos, com ponto no milhar (R$ 21.775).
- Dias e percentuais com 1 casa decimal e vírgula (3,3 dias; 78,8%).
- Valores negativos aparecem com o sinal de menos (−R$ 1.000; −1,0 dias).

### Exemplo da Brasa no Bairro

Fica no bloco **2) DADOS DO EXEMPLO**, no começo do `quadro.html` (perto da linha 42). Os valores estão entre aspas, com o mesmo cuidado do exemplo do `index.html`: troque só o que está entre aspas. O "mês" do exemplo é o número do mês do negócio (mês 3, mês 4), não do calendário.

Resultado esperado:

| Indicador | Valor |
|---|---|
| Capital circulante líquido | R$ 21.775 |
| Necessidade de capital de giro | R$ 17.165 |
| Saldo disponível | R$ 4.610 |
| Desembolso diário | R$ 1.396 |
| Fôlego de caixa livre | 3,3 dias |
| Fôlego de caixa | 4,9 dias |
| Quanto da folga o giro consome | 78,8% |
| Faixa | 2 |
| Meta da faixa 3 | R$ 9.772 |
| Falta | R$ 5.162 |
| Prazo de estoque | 9,8 dias |
| Prazo de recebimento | 16,4 dias |
| Prazo de pagamento | 7,0 dias |
| Ciclo financeiro | 19,2 dias |

### Textos e cores

- O `quadro.html` tem a sua própria cópia do bloco **1) PERSONALIZAÇÃO** (perto da linha 11). **Se mudar o nome do e-book ou as cores no `index.html`, mude também aqui.** O nome do e-book está na linha 16 e ainda é o provisório.
- As frases das faixas ficam em `var FAIXAS` (perto da linha 650).
- As explicações dos indicadores ficam em `var EXPLICA` (perto da linha 641).
- As perguntas do teste ficam em `var PERGUNTAS` (perto da linha 660), e os resultados do teste em `function resultadoTeste` (logo abaixo).
- As sugestões de ação ficam em `var SUGESTOES`.

### Dados

- A página guarda os dados numa gaveta própria, `quadroIndicadores.v1` (linha 623). **Não mude esse nome.** O Controle de retiradas usa outra gaveta, `controleRetiradasDono.v1`, que a página nova só lê para sugerir o total de saídas e nunca altera.
- Cópia de segurança, restauração e planilha ficam em **Menu > Meus dados**, como no Controle de retiradas. Cada página tem a sua cópia: a cópia de uma página não serve na outra, e o site avisa se a pessoa tentar.
