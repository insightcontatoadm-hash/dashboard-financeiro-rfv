# Veterinária 360 — Inteligência da Clínica

Dashboard HTML autocontido inspirado na estrutura visual do RFVC 360: sidebar, módulos, filtros, cards, gráficos, tabelas e metodologia.

## Abrir

Abra `index.html` diretamente no navegador.

## Módulos

- **Clínica:** atendimentos, receita registrada, tutores, animais, espécies, portes, status e itens faturados.
- **Estoque e Produtos:** saldo, valor a custo médio, valor a venda informado, situação do saldo, movimentações e cadastro de produtos.
- **Resultado Financeiro:** recebimentos, pagamentos, pendências e resultado operacional de caixa.
- **Metodologia:** fontes, campos, cálculos e limitações.

## Rastreabilidade

Dados extraídos das cinco bases PostgreSQL da clínica em sessão SSL e somente leitura. O pacote não contém credenciais.

Fontes principais:

- `petshop_atendimentos`
- `petshop_atendimentos_itens`
- `animais`
- `PRODUTOS`
- `PRODUTO_GRUPOS`
- `PRODUTO_SUBGRUPOS`
- `ESTOQUE_MOVIMENTACAO`
- `ESTOQUE_MOVIMENTACAO_TIPO`
- `titulos`

## Atualizar os dados

No diretório principal do projeto, com a VPN conectada e as variáveis de conexão configuradas:

```bash
py veterinaria360_extract.py
py veterinaria360_build.py
```

O resultado da extração é `veterinaria360_data.json`; o HTML final é `veterinaria360/index.html`.

Os indicadores financeiros são explicitamente apresentados como resultado operacional de caixa, não como lucro líquido ou DRE, porque a extração não confirmou uma DRE contábil validada.
