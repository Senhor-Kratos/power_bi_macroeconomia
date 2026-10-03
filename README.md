# Análise Macroeconômica do Brasil | Power BI

Projeto de Business Intelligence para acompanhar a evolução da inflação, da taxa Selic e do câmbio no Brasil, usando séries públicas do Banco Central do Brasil (BCB).

> **Pergunta de negócio:** como inflação, juros e câmbio evoluíram no Brasil e em quais períodos suas trajetórias mudaram?

## Visão geral

O relatório reúne indicadores macroeconômicos em duas páginas:

- **Visão geral:** cartões com indicadores recentes e séries mensais de IPCA, Meta Selic e dólar de venda.
- **Análise anual:** inflação composta por ano, principais leituras, metodologia e fontes.

Os cartões de valor recente devem usar medidas filtradas para a última data disponível. O gráfico anual apresenta o IPCA acumulado de janeiro a dezembro; o ano corrente é parcial.

<!-- Adicione as capturas em uma pasta `assets/` no repositório e remova os comentários abaixo.
![Página 1 — Visão geral](assets/visao-geral.png)
![Página 2 — Análise anual](assets/analise-anual.png)
-->

## Indicadores

| Indicador | Descrição | Série BCB |
|---|---|---:|
| IPCA mensal | Variação mensal do índice de preços (%) | SGS 433 |
| IPCA acumulado | Variação composta em 12 meses ou no ano-calendário (%) | Derivado do SGS 433 |
| Meta Selic | Taxa definida pelo Copom (% ao ano) | SGS 432 |
| Dólar de venda | Taxa de câmbio de venda (R$/US$) | SGS 1 |

## Principais leituras

- 2021 aparece como destaque inflacionário no período analisado.
- A Selic subiu após a aceleração da inflação, com defasagem entre a mudança dos preços e a resposta dos juros.
- A alta do dólar no fim de 2024 coincidiu com uma nova elevação da Selic; a coincidência temporal, por si só, não demonstra causalidade.
- Após o pico de 2021, a inflação anual diminuiu, embora tenha permanecido acima de zero nos anos seguintes.

As leituras são descritivas. O painel permite explorar a evolução conjunta das séries, mas não identifica relações causais.

## Dados e metodologia

- Dados obtidos das séries temporais públicas do Sistema Gerenciador de Séries Temporais (SGS) do BCB.
- Selic e dólar, originalmente diários, são resumidos pela última observação disponível de cada mês.
- A inflação acumulada é calculada por composição geométrica das taxas mensais: `((1 + IPCA₁) × ... × (1 + IPCAₙ)) − 1`.
- O acumulado em 12 meses usa os 12 meses terminados na data de referência. Para o gráfico anual, o acumulado considera janeiro a dezembro.
- A inflação do ano corrente é parcial até o último mês publicado.
- Os valores podem mudar quando as consultas são atualizadas ou quando as séries oficiais recebem revisões.

## Tecnologias

- Microsoft Power BI Desktop
- Power Query (linguagem M) para consulta e preparação dos dados
- DAX para medidas e indicadores
- API pública do BCB / SGS

## Arquivos do projeto

- [`Macroeconomia_Brasil.pbix`](Macroeconomia_Brasil.pbix) — relatório Power BI.
- capturas de tela do relatório:
<img width="2995" height="1674" alt="Macroeconomia_Brasil Copy2 Copy_pages-to-jpg-0001" src="https://github.com/user-attachments/assets/57c92ab8-8f6d-4b78-b994-91e0d4cc38b8" />
<img width="2995" height="1671" alt="Macroeconomia_Brasil Copy2 Copy_pages-to-jpg-0002" src="https://github.com/user-attachments/assets/203393e6-1588-4a92-856c-3c8065d7ff5b" />



## Fontes oficiais

- IPCA mensal — SGS 433
- Meta Selic — SGS 432
- Dólar, venda — SGS 1
- Banco Central do Brasil — SGS

## Como visualizar

1. Baixe `Macroeconomia_Brasil.pbix` deste repositório.
2. Abra o arquivo no Power BI Desktop.
3. Atualize as consultas para buscar os dados mais recentes do BCB, se necessário.

---

Projeto demonstrativo de análise de dados com informações públicas. Os resultados não constituem recomendação de investimento.
