# BI em 30 dias — Análise de Dados com foco em Business Intelligence

Plano de estudos de 30 dias para construir uma base sólida em análise de dados e BI, aplicada a dados econômicos reais do Brasil.

- **Perfil:** estudante de Ciências Econômicas (UFPB), iniciante em programação
- **Carga:** 1 hora por dia, 30 horas no total
- **Projeto que atravessa o plano:** *Inflação, juros e consumo no Brasil (2015–2026)*

## Objetivo

Em 30 horas não dá para dominar cinco ferramentas. O objetivo é entender o fluxo completo de um projeto de BI e conseguir executá-lo de ponta a ponta:

> pergunta → coleta → limpeza → consulta → análise → visualização → comunicação

Ao final dos 30 dias:

| Área | O que você vai saber fazer |
|---|---|
| Planilhas | Importar e limpar séries do Banco Central; referências absolutas, PROCX/PROCV, SE, MÉDIASE; tabela dinâmica e gráfico de linha legível |
| SQL | SELECT, WHERE, ORDER BY, GROUP BY, HAVING, CASE e JOIN entre 2 ou 3 tabelas (SQLite) |
| Python | Variáveis, condicionais, laços e funções; com Pandas: ler CSV, filtrar, criar colunas, juntar e agrupar |
| Estatística aplicada | Calcular e interpretar média, mediana, variância, desvio padrão, coeficiente de variação e correlação (correlação não é causalidade) |
| Power BI | Power Query, tabela calendário, 4 a 6 medidas DAX simples e dashboard de 2 páginas |
| Portfólio | Projeto publicado no GitHub com README e conclusões econômicas |

**Fica de fora, de propósito:** machine learning, regressão e inferência, DAX avançado, Python avançado e modelagem de bancos de dados. São os próximos passos.

**Diferencial:** muitos candidatos sabem usar as ferramentas; poucos sabem explicar por que a Selic sobe depois da inflação, o que é juro real ou por que o consumo reage com defasagem. Todos os exercícios treinam técnica + interpretação econômica.

## Rotina de cada sessão (1 hora)

| Bloco | Tempo | O que fazer |
|---|---|---|
| Teoria | 15 min | Aula ou leitura curta. Anote só conceitos e sintaxe. |
| Prática | 35 min | Exercício do dia, com dados reais, sempre salvo no projeto. |
| Revisão | 10 min | 1) Refaça de memória o comando principal; 2) registre no diário o que aprendeu, um erro e uma dúvida; 3) nos dias de avaliação, releia o diário da semana. |

**Regra de ouro:** se o exercício não terminar, não acumule. Faça a revisão e retome no dia seguinte. Os dias de avaliação (7, 14, 22 e 30) têm folga para isso.

**Organização no Drive:** pasta `BI-30dias` com as subpastas `dados_brutos`, `dados_tratados`, `sql`, `python` e `powerbi`.

**Requisito técnico:** o Power BI Desktop só roda no Windows. Em Mac, Linux ou Chromebook, faça a Semana 4 no Looker Studio (os conceitos de visualização são os mesmos; só o DAX fica de fora).

## Visão geral das 4 semanas

| Semana | Dias | Foco | Entrega |
|---|---|---|---|
| 1 | 1–7 | Planilhas + estatística descritiva | Base mensal IPCA + Selic limpa, tabela dinâmica e 2 gráficos |
| 2 | 8–14 | SQL | Banco SQLite com 2 tabelas e cerca de 10 consultas salvas |
| 3 | 15–22 | Python (lógica + Pandas) + correlação | Notebook no Colab que baixa, trata e analisa os dados + `base_final.csv` |
| 4 | 23–30 | Power BI + projeto final | Dashboard de 2 páginas + README no GitHub |

**Por que esta ordem?** Planilha → SQL → Python → Power BI aumenta a abstração aos poucos. A estatística aparece onde é usada (descritiva na Semana 1, correlação na Semana 3). O mesmo conjunto de dados atravessa as quatro semanas: cada ferramenta refaz e amplia o trabalho da anterior, e o plano inteiro vira um único projeto de portfólio.

Roteiro dia a dia: [cronograma.md](cronograma.md) · Materiais: [recursos.md](recursos.md) · Diário: [anotacoes/](anotacoes/)

## Projeto prático: Inflação, juros e consumo no Brasil (2015–2026)

**Pergunta de pesquisa:** como a inflação (IPCA) e a taxa Selic evoluíram entre 2015 e 2026, e o volume de vendas do varejo reage aos juros com defasagem?

### Dados

| Indicador | Fonte | Onde encontrar | Frequência |
|---|---|---|---|
| IPCA — variação mensal (%) | Banco Central (SGS), origem IBGE | Série 433 | Mensal |
| Selic acumulada no mês, anualizada (% a.a.) | Banco Central (SGS) | Série 4189 | Mensal |
| Volume de vendas do varejo (índice) | IBGE — PMC | SIDRA › Pesquisa Mensal de Comércio | Mensal |
| Meta de inflação (opcional) | CMN / Banco Central | Site do BCB | Anual |

Antes de usar cada série, confira no SGS ou no SIDRA o nome exato, a unidade e o período disponível, e registre isso no dicionário de variáveis.

### Indicadores calculados

- **IPCA acumulado em 12 meses:** produto de (1 + IPCA mensal/100) dos últimos 12 meses, menos 1
- **Juro real ex post (Fisher):** (1 + Selic) / (1 + IPCA 12m) − 1
- **Varejo:** variação percentual do índice em 12 meses
- **Relação juros-consumo:** correlação entre a Selic defasada (6 e 12 meses) e o varejo

### Etapas por semana

| Semana | Ferramenta | O que você faz no projeto |
|---|---|---|
| 1 | Google Sheets | Coleta, limpeza e unificação de IPCA + Selic; IPCA 12m; estatísticas descritivas; primeiros gráficos |
| 2 | SQL (SQLite) | Tabelas `macro_mensal` e `varejo`; agregações por ano; JOIN dos três indicadores |
| 3 | Python (Pandas) | Coleta automática pela API, merge, juro real, correlações com defasagem → `base_final.csv` |
| 4 | Power BI | Power Query, tabela calendário, medidas DAX, dashboard de 2 páginas e README no GitHub |

### Entregáveis e limitações

- **Entregáveis:** planilha tratada, `consultas.sql`, notebook do Colab, arquivo `.pbix` com prints e README com 3 a 5 conclusões econômicas.
- **Limitações a declarar:** correlação não prova causalidade; renda, crédito, transferências de renda e a pandemia de 2020 também afetam o varejo; o período é curto.
- **Extensões futuras:** IBC-Br, desemprego (PNAD Contínua), expectativas do Boletim Focus e câmbio.

## Avaliações

Avaliações nos dias **7, 14, 22 e 30**, feitas sem consultar o material e corrigidas depois. Os exercícios e critérios de cada uma estão no [cronograma](cronograma.md).

**Regra para avançar:** cumprir pelo menos 80% dos critérios da semana. Se não atingir, use a primeira sessão da semana seguinte para refazer o que falhou e adie em um dia o conteúdo novo. Não pule etapas.

## Depois dos 30 dias

- **Aprofundar:** SQL com funções de janela e Pandas com séries temporais
- **Conectar com a graduação:** estatística inferencial e regressão em Python (ponte para Econometria)
- **Segundo projeto:** dashboard de indicadores de empresas listadas, com o material de Análise de balanço e os dados abertos da CVM
- **Certificação:** PL-300 (Microsoft Power BI Data Analyst), como meta de médio prazo
- **Visibilidade:** publicar o projeto no LinkedIn e atualizar o currículo com as ferramentas e o link do GitHub
