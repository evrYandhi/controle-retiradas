# Controle de retiradas do dono

Ferramenta do Capítulo 1 do e-book. Ajuda o dono de um negócio pequeno a anotar o dinheiro que tira da empresa para uso pessoal e a comparar esse total com o que a empresa deixou no mês.

O site inteiro é um arquivo só: **index.html**. Não precisa instalar nada e funciona sem internet depois de aberto.

---

## 1. Como abrir o site

**No computador**

1. Baixe o arquivo `index.html` para uma pasta do computador.
2. Dê dois cliques nele. Ele abre no navegador (Chrome, Edge, Firefox ou Safari).

**No celular**

Abrir um arquivo solto no celular costuma dar trabalho. O caminho mais simples é publicar o site (seção 4) e abrir o link no navegador do celular.

**Atenção:** os dados que uma pessoa digita ficam guardados no navegador, ligados ao endereço por onde ela abriu o site. Se você testar abrindo o arquivo no computador e depois abrir o link publicado, vai ver duas listas diferentes. Isso é normal.

---

## 2. Como trocar os dados do exemplo

Os dados do botão "Ver um exemplo" ficam no começo do arquivo `index.html`, no bloco que começa com:

```
2) DADOS DO EXEMPLO
```

Ele fica mais ou menos na linha 46 e tem este formato:

```
var EXEMPLO = {
  mes: 10,      // 1 = janeiro ... 12 = dezembro
  ano: 2026,
  entrou: "6.000",
  gastou: "3.500",
  retiradaFixa: "",
  retiradas: [
    ["03/10", "Mercado", "420"],
    ["05/10", "Aluguel de casa", "950"],
    ...
    ["26/10", "Mercado", "150"]
  ]
};
```

Regras para não quebrar o site:

- Troque só o que está **entre aspas** e os números de `mes` e `ano`.
- Valores podem ser escritos como no dia a dia: `"1200"`, `"1.200"` ou `"1.200,50"`.
- Sem retirada fixa: deixe `retiradaFixa: ""` (aspas vazias). Com retirada fixa: `retiradaFixa: "2.000"`.
- Cada retirada é uma linha `["dia/mês", "para que foi", "valor"],`.
- **Toda linha de retirada termina com vírgula, menos a última.**
- Para tirar uma retirada, apague a linha inteira. Para pôr uma nova, copie uma linha e mude o conteúdo.

Depois de salvar, abra o site, toque em **Menu** e depois em **Ver um exemplo** para conferir.

---

## 3. Como mudar cores, fonte e textos

### Nome do e-book, cores e fonte

Ficam no bloco **1) PERSONALIZAÇÃO**, logo no começo do arquivo (perto da linha 11):

```
var PERSONALIZACAO = {
  nomeDoEbook: "E-book de Gestão Financeira",
  capitulo: "Capítulo 1",
  nomeDaFerramenta: "Controle de retiradas do dono",
  fonte: '...',
  cores: {
    fundo: "#F2F5F3",
    principal: "#2B5A87",
    ...
  },
  motivosRapidos: ["Mercado", "Aluguel de casa", ...]
};
```

- **Nome do e-book:** troque `"E-book de Gestão Financeira"` pelo nome verdadeiro. Ele aparece no topo, no rodapé e na folha impressa.
- **Cores:** cada cor é um código que começa com `#` seguido de 6 letras ou números. Para achar o código de uma cor, pesquise "seletor de cores" no Google, escolha a cor e copie o código que aparece ao lado de "HEX". Ao lado de cada cor no arquivo há um comentário dizendo onde ela aparece.
- **Cuidado com o contraste:** texto claro sobre fundo claro fica ilegível. O verde (`coube`) e o vermelho (`passou`) precisam continuar escuros o bastante para ler sobre o fundo clarinho deles.
- **Botões rápidos de motivo:** é a lista `motivosRapidos`. Mantenha "Outro" no final.

Para padronizar com as ferramentas dos outros capítulos, basta copiar esse bloco inteiro de um arquivo para o outro.

### Outros textos

As frases das telas estão espalhadas pelo arquivo. Para mudar uma:

1. Abra o arquivo para editar (veja abaixo).
2. Use a busca (Ctrl+F no Windows, Cmd+F no Mac) e digite um pedaço da frase.
3. Troque só as palavras, sem apagar aspas, sinais `<` `>` ou o que estiver em volta.

O passo a passo das 3 telas fica no bloco `var PASSOS` (perto da linha 674). O texto "O que conta como retirada" fica em `var EXPLICA_RETIRADA`, logo abaixo.

**Não mude** a linha `var CHAVE = "controleRetiradasDono.v1";`. Ela é o nome da gaveta onde os dados de cada pessoa ficam guardados. Se mudar, quem já usa o site vai abrir a ferramenta vazia.

### Como abrir o arquivo para editar

- **Mais fácil, depois de publicado no GitHub:** abra o arquivo `index.html` na página do repositório e clique no ícone de lápis ("Edit this file"). Edite, clique em **Commit changes...** e confirme em **Commit changes**. O site atualiza sozinho em 1 ou 2 minutos.
- **No Windows:** clique com o botão direito em `index.html`, escolha **Abrir com** e depois **Bloco de Notas**. Salve com Ctrl+S.
- **No Mac:** o TextEdit pode estragar o arquivo. Prefira editar pelo GitHub.

Depois de qualquer mudança, abra o site e confira se tudo aparece. Se a tela ficar em branco, quase sempre faltou uma aspa ou uma vírgula. Desfaça a última mudança.

---

## 4. Como publicar (resumo)

Recomendação: **GitHub Pages, dentro de uma organização do grupo**. O passo a passo completo está na conversa com o Claude e resumido aqui:

1. Cada integrante cria uma conta gratuita em github.com.
2. Uma pessoa cria uma **organização gratuita** (botão **+** no canto de cima, depois **New organization**, plano **Free**).
3. Todos os integrantes viram **Owner** (dono) da organização. Se puderem, incluam também o professor ou alguém do curso.
4. Dentro da organização, criem um repositório **público** chamado, por exemplo, `controle-retiradas`.
5. Enviem o `index.html` para o repositório (link **uploading an existing file**).
6. Em **Settings**, depois **Pages**: Source **Deploy from a branch**, Branch **main**, pasta **/ (root)**, e **Save**.
7. O link fica assim: `https://NOME-DA-ORGANIZACAO.github.io/controle-retiradas/`

**Decidam o nome da organização antes de divulgar o link.** Os dados das pessoas ficam presos ao endereço. Se o nome da organização mudar, quem já usa a ferramenta abre o site vazio e só recupera os dados com a cópia de segurança.

---

## 5. O que a ferramenta guarda e onde

- Tudo fica no navegador do aparelho da pessoa. Não há cadastro nem servidor, e nada é enviado para a internet.
- Se a pessoa limpar o navegador, os dados somem. Por isso existe o botão "Fazer cópia de segurança".
- No iPhone, o Safari pode apagar os dados de sites que ficam muitos dias sem uso. O site mostra uma dica para adicionar a ferramenta à tela de início, o que reduz esse risco.

## 6. Testes

A pasta `testes` tem as fotos das telas e o relatório dos testes automáticos (`resultados.json`). Ela não precisa ser publicada.
