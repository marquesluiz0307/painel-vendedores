# 📊 Painel de Acompanhamento de Vendedores (Drill-Down)

Dashboard executivo desenvolvido para acompanhamento diário e acumulado de metas comerciais por filial e vendedor, integrado em tempo real com planilhas do Google Sheets.

## 🚀 Funcionalidades Principais

- **Visão Geral Diária (Matriz):** Mapa de calor horizontal com colunas congeladas (`Filial`, `Vendedor` e `Meta Inicial`), destacando automaticamente em **verde** os dias em que a meta foi batida e em **vermelho** os dias abaixo do objetivo.
- **Acompanhamento Drill-Down & Meta:** Filtragem interativa por **Filial** e **Data de Referência** (dia específico ou acumulado do período), exibindo percentual de atingimento e o cálculo exato do **Saldo Devedor (`Meta - Realizado`)** de cada vendedor.
- **Detalhamento Individual:** Modal interativo com gráfico de evolução diária (`Chart.js`) e extrato completo dia a dia ao clicar em qualquer vendedor.
- **Sincronização Automática:** Leitura direta do CSV publicado no Google Sheets com atualização automática a cada 60 segundos e detecção inteligente de dias futuros (ignorando células vazias ou erros `#N/D` de `PROCV` sem distorcer o acumulado).

## 🛠️ Tecnologias Utilizadas

- **HTML5 & JavaScript (ES6+)** — Aplicação single-file leve, sem necessidade de build ou servidor backend.
- **Tailwind CSS** — Estilização responsiva e interface moderna.
- **Chart.js** — Visualização gráfica de desempenho diário por vendedor.
- **Cloudflare Pages** — Hospedagem estática de alta disponibilidade integrada ao GitHub.

## 🔄 Como Atualizar os Dados

Não é necessário alterar o código ou realizar novos deploys para atualizar os números do painel:

1. Preencha a aba correspondente ao dia na planilha base do Google Sheets.
2. Garanta que os valores sejam refletidos na aba consolidada (via `PROCV` ou fórmula equivalente).
3. O painel detecta automaticamente as novas colunas preenchidas e recalcula todos os indicadores.
