# 3D Print Manager

Aplicacao web (single file) para calcular precificacao de pecas 3D, controlar impressoras, salvar projetos e gerar relatorios em PDF.

## Visao geral

Este projeto roda inteiramente no navegador e usa `localStorage` para persistir dados.

Arquivo principal:
- `index.html`

## Funcionalidades

- Calculadora de preco com:
- custo de filamento
- custo de energia
- custo de embalagem
- custos adicionais dinamicos
- amortizacao por hora
- taxas (falhas, imposto, cartao, anuncios)
- markup final
- Cadastro de impressoras com:
- nome, modelo, custo, potencia e vida util
- calculo de amortizacao por hora (`custo / vidaUtilHoras`)
- controle de horas utilizadas
- Cadastro e gestao de projetos:
- salvar projeto calculado
- carregar projeto para recalculo
- excluir projeto
- exportar projeto para PDF
- Dashboard com graficos:
- projetos por mes
- faturamento por mes
- uso por impressora
- distribuicao de custos
- Exportacao de orcamento/relatorio em PDF (via preview + download)

## Stack

- HTML + JavaScript puro
- Tailwind CSS via CDN
- Chart.js via CDN
- jsPDF via CDN
- html2canvas via CDN
- Google Fonts (Poppins) via CDN

## Como executar

1. Abra `index.html` no navegador.
2. Use a aba **Impressoras** para cadastrar pelo menos uma impressora.
3. Na aba **Calculadora**, preencha os dados da peca e clique em **Calcular Preco**.
4. Clique em **Salvar Projeto** para gravar no `localStorage`.
5. Use **Exportar PDF** para gerar o orcamento.

Depois abra `http://localhost:8080`.

## Persistencia de dados

Os dados sao armazenados no navegador com as chaves:

- `impressoras`
- `projetos`

Para limpar os dados, apague essas chaves no DevTools (`Application > Local Storage`).

## Estrutura do projeto

```text
.
|- index.html
|- README.md
|- LICENSE
```

## Observacoes

- O projeto depende de internet para carregar bibliotecas CDN.
- Nao ha backend, autenticacao ou banco de dados server-side.
