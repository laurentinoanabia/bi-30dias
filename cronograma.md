# Cronograma — semanas 1 a 4

Cada dia é uma sessão de 1 hora: **15 min de teoria + 35 min de prática + 10 min de revisão**. A revisão segue sempre a mesma rotina: refazer de memória o comando principal do dia e registrar aprendizado, erro e dúvida no diário ([anotacoes/](anotacoes/)).

Links em [recursos.md](recursos.md). Marque `[x]` ao concluir cada dia.

| Semana | Dias | Foco | Entrega |
|---|---|---|---|
| [1](#semana-1--planilhas-e-estatística-descritiva-dias-17) | 1–7 | Planilhas + estatística descritiva | Base IPCA + Selic limpa, tabela dinâmica e 2 gráficos |
| [2](#semana-2--sql-dias-814) | 8–14 | SQL | Banco SQLite com 2 tabelas e ~10 consultas salvas |
| [3](#semana-3--python-pandas-e-correlação-dias-1522) | 15–22 | Python + Pandas + correlação | Notebook no Colab + `base_final.csv` |
| [4](#semana-4--power-bi-e-projeto-final-dias-2330) | 23–30 | Power BI + projeto | Dashboard de 2 páginas + README no GitHub |

---

## Semana 1 — Planilhas e estatística descritiva (Dias 1–7)

**Objetivo:** organizar e limpar dados, usar as fórmulas essenciais e resumir uma série com média, mediana e desvio padrão. A planilha é a porta de entrada de qualquer estágio.
**Entrega:** base mensal IPCA + Selic limpa, tabela dinâmica e 2 gráficos.

| ✓ | Dia e tema | Teoria (15 min) | Prática (35 min) | Resultado esperado |
|---|---|---|---|---|
| [ ] | **Dia 1** — O trabalho de BI e os primeiros dados | Ciclo do BI (pergunta → dados → tratamento → análise → visualização → decisão). O que é uma série temporal. O SGS do Banco Central. | Criar a pasta `BI-30dias` no Drive. Baixar o IPCA mensal (SGS 433) em CSV pela API e importar no Google Sheets (Arquivo › Importar). Criar o diário de bordo e escrever, em 3 linhas, a pergunta do projeto. | Planilha `projeto_macro` com a aba `ipca_bruto`; pergunta do projeto escrita. |
| [ ] | **Dia 2** — Fórmulas e referências | Operadores; referências relativas x absolutas (`$A$1`); SOMA, MÉDIA, MÍNIMO, MÁXIMO, CONT.NÚM. | Calcular nº de meses, maior e menor IPCA mensal (e quando ocorreram, com filtro) e média geral. Criar a coluna `fator` = 1 + IPCA/100. Congelar o cabeçalho e formatar os números. | Bloco de resumo com 5 fórmulas corretas; você sabe quando usar `$`. |
| [ ] | **Dia 3** — Limpeza e organização | Dados organizados (uma variável por coluna, uma observação por linha). Vírgula x ponto decimal, datas como texto, espaços, duplicatas. ARRUMAR, SUBSTITUIR, DATA, VALOR. | Baixar a Selic acumulada no mês anualizada (SGS 4189). Padronizar as datas, converter textos em números, remover duplicatas e criar a aba `dados_tratados`: `data` \| `ipca_mensal` \| `selic_aa`. | Aba limpa, sem erros e com tipos corretos (teste: a MÉDIA funciona em todas as colunas numéricas). |
| [ ] | **Dia 4** — Busca e lógica | PROCX (XLOOKUP) e PROCV; SE, E, OU, SEERRO; ANO() e MÊS(). | Trazer a Selic para cada mês do IPCA com PROCX. Criar as colunas `ano`, `mes` e `faixa_ipca` = SE(ipca>0,5; "alta"; SE(ipca<0; "deflação"; "moderada")). | Base unificada IPCA + Selic com colunas auxiliares. |
| [ ] | **Dia 5** — Estatística descritiva I e juros compostos | Média x mediana x moda; efeito de valores extremos. Por que o IPCA acumulado em 12 meses é um produto de fatores, e não uma soma. | Criar `ipca_12m` = PRODUTO dos 12 últimos fatores − 1 (a partir da 12ª linha). Por ano: média (MÉDIASE) e mediana do IPCA mensal. Comparar o IPCA 12m de dezembro de cada ano com a meta de inflação. | IPCA 12m conferido com um valor oficial do IBGE (diferença próxima de zero). |
| [ ] | **Dia 6** — Tabelas dinâmicas e gráficos | Estrutura da tabela dinâmica (linhas, colunas, valores, filtros). Boas práticas: título que diz a conclusão, fonte, eixos legíveis, nada de 3D. | Tabela dinâmica: ano × (média do IPCA, média da Selic, nº de meses de deflação). Gráfico de linhas IPCA 12m x Selic. Abrir uma cópia da planilha "Monitor 2026" e observar a organização das tabelas setoriais. | 1 tabela dinâmica + 2 gráficos com título-conclusão e fonte (BCB/IBGE). |
| [ ] | **Dia 7** — Variabilidade + Avaliação 1 | Variância, desvio padrão (DESVPAD.A) e coeficiente de variação (DP/média). Pergunta-guia: "quão instável foi a inflação?" | Calcular DP e CV do IPCA mensal por ano e responder: qual ano teve a inflação mais instável? Depois, fazer a Avaliação 1. | Avaliação 1 concluída; decisão de avançar ou reforçar. |

### Avaliação 1 — Planilhas e estatística (Dia 7)

Faça sem consultar o material; corrija depois.

**Exercícios**
- [ ] **Importação:** em uma planilha nova, importe o IPCA dos últimos 24 meses e calcule o IPCA 12m do último mês, sem consultar suas anotações.
- [ ] **Referências:** explique por escrito a diferença entre `A1`, `$A1` e `$A$1`.
- [ ] **Tabela dinâmica:** monte uma tabela com a média da Selic por ano.
- [ ] **Estatística:** calcule média, mediana e desvio padrão do IPCA mensal de 2021 e explique, em duas frases, o que o desvio padrão indica.
- [ ] **Comunicação:** faça um gráfico com título-conclusão (ex.: "A Selic subiu após a aceleração da inflação em 2021").

**Critérios para avançar (mínimo 80%)**
- [ ] IPCA 12m com diferença menor que 0,05 p.p. em relação ao valor oficial do IBGE
- [ ] Fórmulas sem números digitados à mão no meio dos cálculos
- [ ] Colunas com tipos corretos (datas como datas, números como números)
- [ ] Tabela dinâmica correta e interpretação estatística coerente
- [ ] Gráfico com título, fonte e eixos legíveis

---

## Semana 2 — SQL (Dias 8–14)

**Objetivo:** consultar dados de forma estruturada: filtrar, agregar e cruzar tabelas. É a habilidade mais pedida em vagas de dados e BI.
**Entrega:** banco SQLite com 2 tabelas e cerca de 10 consultas salvas.

| ✓ | Dia e tema | Teoria (15 min) | Prática (35 min) | Resultado esperado |
|---|---|---|---|---|
| [ ] | **Dia 8** — Bancos de dados relacionais | Banco, tabela, linha, coluna, chave primária e tipos (INTEGER, REAL, TEXT). SQLite: um banco inteiro em um arquivo. | Exportar `dados_tratados` em CSV. No SQLite Online (ou DB Browser), importar como a tabela `macro_mensal`. SQLBolt, lições 1–2. Rodar `SELECT * ... LIMIT 10` e selecionar colunas específicas. | Tabela `macro_mensal` criada e consultada; arquivo `consultas.sql` iniciado. |
| [ ] | **Dia 9** — Filtros e ordenação | WHERE; `=`, `>`, `<`; AND, OR; BETWEEN, IN, LIKE, IS NULL; ORDER BY e LIMIT. | SQLBolt, lições 3–4. Consultas: (a) meses com IPCA > 1%; (b) meses de deflação; (c) 2020–2022 ordenado pela Selic; (d) os 5 maiores IPCAs mensais. | 4 consultas corretas, cada uma com um comentário (`-- ...`) explicando a pergunta econômica. |
| [ ] | **Dia 10** — Agregações | COUNT, SUM, AVG, MIN, MAX; GROUP BY; extrair o ano com `strftime('%Y', data)` ou usar a coluna `ano`. | SQLBolt, lições 10–11. Média do IPCA e da Selic por ano; meses de deflação por ano; ano com a maior Selic média. Comparar com a tabela dinâmica da Semana 1. | Resultados idênticos aos da planilha. |
| [ ] | **Dia 11** — HAVING e CASE | WHERE x HAVING; CASE WHEN para criar categorias; apelidos (AS); ROUND. | SQLBolt, lição 12. (a) Anos com média do IPCA mensal > 0,4% (HAVING). (b) Classificar cada mês em "juros altos" (Selic ≥ 10), "intermediários" (6 a 10) e "baixos" (< 6) com CASE e contar meses por regime. | Consultas com HAVING e CASE funcionando. |
| [ ] | **Dia 12** — JOIN: cruzando informações | INNER JOIN x LEFT JOIN; chave de junção; linhas sem correspondência. Reler a parte de chaves de junção do "Plano de dados" (TPAE II). | Baixar do SIDRA/IBGE o índice de volume de vendas do varejo (PMC), limpar no Sheets e importar como a tabela `varejo`. SQLBolt, lições 6–7. JOIN por data; explicar quantas linhas ficaram sem par no LEFT JOIN e por quê. | Consulta com os 3 indicadores lado a lado (IPCA, Selic, varejo). |
| [ ] | **Dia 13** — Subconsultas e CTE | Subconsulta no WHERE; CTE com WITH para organizar consultas longas. | Criar a CTE `resumo_anual` (médias anuais de IPCA, Selic e varejo) e listar os anos em que o varejo ficou acima da média da série. Exportar em CSV. Opcional: Kaggle "Intro to SQL", lição 1. | `consultas.sql` com ~10 consultas organizadas; CSV exportado. |
| [ ] | **Dia 14** — Avaliação 2 | Revisar o diário e a ordem lógica do SQL: FROM → WHERE → GROUP BY → HAVING → SELECT → ORDER BY. | Fazer a Avaliação 2 sem consultar as consultas anteriores; depois corrigir. | Avaliação 2 concluída; decisão de avançar ou reforçar. |

### Avaliação 2 — SQL (Dia 14)

Escreva sem consultar suas consultas anteriores.

**Exercícios**
- [ ] **Ordenação:** os 10 meses com a maior Selic, do maior para o menor.
- [ ] **Agregação:** média do IPCA por ano, apenas para os anos com média acima de 0,4%.
- [ ] **Categorias:** número de meses em cada regime de juros, usando CASE.
- [ ] **Cruzamento:** um JOIN que mostre IPCA, Selic e varejo de 2023.
- [ ] **Conceitos:** explique a diferença entre INNER JOIN e LEFT JOIN e entre WHERE e HAVING.

**Critérios para avançar**
- [ ] Pelo menos 4 das 5 respostas corretas e rodando sem erro
- [ ] Resultados iguais aos obtidos na planilha
- [ ] Código legível: palavras-chave em maiúsculas, quebras de linha e comentários

---

## Semana 3 — Python, Pandas e correlação (Dias 15–22)

**Objetivo:** aprender lógica de programação do zero e automatizar em Pandas o que foi feito à mão na planilha; medir correlação com defasagem.
**Entrega:** notebook no Colab que baixa, trata e analisa os dados + `base_final.csv`.

| ✓ | Dia e tema | Teoria (15 min) | Prática (35 min) | Resultado esperado |
|---|---|---|---|---|
| [ ] | **Dia 15** — Primeiro programa | O que é programar; Google Colab; `print()`, variáveis, tipos (int, float, str, bool) e operadores. Curso em Vídeo, Python Mundo 1 (aulas iniciais). | Criar `python_bi.ipynb`. Definir `selic` e `ipca` e calcular o juro real (Fisher): `(1 + selic) / (1 + ipca) − 1`. Exibir com f-string. Abrir os notebooks da disciplina e marcar o que já reconhece. | Primeiro notebook rodando sem erros; você identifica o tipo de cada variável com `type()`. |
| [ ] | **Dia 16** — Condicionais | `if` / `elif` / `else`; comparações e operadores lógicos (and, or, not); indentação. | Programa que recebe um IPCA 12m e informa "abaixo do piso", "dentro do intervalo" ou "acima do teto" (meta de 3,0% ± 1,5 p.p.). Testar com 5 valores, incluindo os limites 1,5 e 4,5. | Classificador correto em todos os testes, inclusive nos limites. |
| [ ] | **Dia 17** — Listas e repetição | Listas, índices e `len()`; `for` e `range()`; `while`; variáveis acumuladoras. | Lista com os 12 IPCAs mensais de um ano (da planilha). Com `for`: calcular o acumulado (produto de fatores), contar meses acima de 0,5% e achar o maior valor sem usar `max()`. | Acumulado igual ao da planilha no Dia 5. |
| [ ] | **Dia 18** — Funções e dicionários | `def`, parâmetros, `return` e valores padrão; por que funções evitam repetição. Dicionários (chave: valor). | Criar `acumular(lista)`, `juro_real(selic, ipca)` e `classificar_meta(ipca_12m)`. Montar `{ano: lista_de_ipcas}` e, com um `for`, imprimir o acumulado e a classificação de cada ano. | 3 funções reutilizáveis + mini-relatório anual impresso. |
| [ ] | **Dia 19** — Pandas I | Series x DataFrame; `read_csv`, `head`, `info`, `describe`, `dtypes`; `pd.to_datetime`. | Ler IPCA e Selic direto da API do BCB com `pd.read_csv(url, sep=";", decimal=",")`, converter as datas (`dayfirst=True`) e explorar com `info()` e `describe()`. Comparar com as estatísticas da Semana 1. | Dois DataFrames carregados automaticamente, sem baixar arquivos à mão. |
| [ ] | **Dia 20** — Pandas II | Seleção de colunas, `loc` e filtros booleanos; novas colunas; `merge` (= JOIN); `groupby` (= GROUP BY). | `merge` de IPCA + Selic + varejo pela data; `ipca_12m` com `rolling(12)` e a coluna `juro_real`; `groupby` por ano com médias. Exportar `base_final.csv` para o Drive. | `base_final.csv` pronta para o Power BI; você enxerga a equivalência Planilha ↔ SQL ↔ Pandas. |
| [ ] | **Dia 21** — Correlação | Covariância e correlação de Pearson (−1 a +1); correlação não é causalidade; defasagem da política monetária; dispersão. StatQuest ou Khan Academy. | `df.corr()` entre Selic, IPCA 12m e varejo. Usar `shift(6)` e `shift(12)` na Selic e comparar as correlações com o varejo. Gráfico de dispersão + um parágrafo de interpretação econômica, com cautela. | Tabela de correlações com e sem defasagem + parágrafo interpretativo. |
| [ ] | **Dia 22** — Avaliação 3 | Revisar o diário e reler o notebook de cima a baixo. | Fazer a Avaliação 3. Organizar o notebook com títulos em Markdown e comentários. | Notebook limpo, que roda do zero (Ambiente de execução › Reiniciar e executar tudo). |

### Avaliação 3 — Python, Pandas e correlação (Dia 22)

**Exercícios**
- [ ] **Funções:** escreva do zero uma função que recebe uma lista de IPCAs mensais e devolve o acumulado.
- [ ] **Lógica:** use `for` e `if` para contar os meses de deflação em uma lista.
- [ ] **Pandas:** leia a Selic pela API, filtre 2022–2024 e calcule a média por ano.
- [ ] **Merge:** junte duas tabelas e verifique o número de linhas antes e depois.
- [ ] **Interpretação:** o que sugere uma correlação de −0,4 entre a Selic defasada e o varejo? E o que ela não prova?

**Critérios para avançar**
- [ ] O notebook roda inteiro depois de "Reiniciar e executar tudo"
- [ ] Você consegue explicar em voz alta o que cada linha faz
- [ ] Nomes de variáveis claros (`ipca_12m`, e não `x2`)
- [ ] A interpretação menciona causalidade, defasagem e outros fatores

---

## Semana 4 — Power BI e projeto final (Dias 23–30)

**Objetivo:** transformar a análise em um dashboard e comunicar conclusões como um analista.
**Entrega:** dashboard de 2 páginas + README no GitHub.

> Sem Windows? Faça esta semana no Looker Studio: os conceitos de visualização são os mesmos, só o DAX fica de fora.

| ✓ | Dia e tema | Teoria (15 min) | Prática (35 min) | Resultado esperado |
|---|---|---|---|---|
| [ ] | **Dia 23** — Primeiro contato com o Power BI | Interface (relatório, dados, modelo) e fluxo: obter dados → Power Query → modelo → visuais. Microsoft Learn, módulo introdutório. | Instalar o Power BI Desktop e importar `base_final.csv`. No Power Query: conferir tipos (data, decimal), renomear e remover colunas desnecessárias; Fechar e aplicar. | Arquivo `projeto_macro.pbix` com os dados carregados corretamente. |
| [ ] | **Dia 24** — Power Query | Etapas aplicadas; coluna personalizada; mesclar consultas (= JOIN) e acrescentar consultas (= UNION). A linguagem M existe, mas você usará a interface. | Importar o CSV bruto do varejo e mesclá-lo com a base no Power Query (refazendo o JOIN do Dia 12). Criar colunas Ano e Mês e observar as etapas aplicadas. | Tratamento reproduzível: tudo se refaz com um clique em "Atualizar". |
| [ ] | **Dia 25** — Modelagem | Tabela fato x dimensão; esquema estrela; relacionamento 1:N; por que usar uma tabela calendário. | Criar `dCalendario` com DAX: `CALENDAR(DATE(2015,1,1), DATE(2026,12,31))` (no Power BI em português o separador pode ser `;`). Adicionar Ano e Mês, marcar como tabela de datas e relacionar com a base. | Modelo com relacionamento 1:N funcionando (o filtro de ano afeta os visuais). |
| [ ] | **Dia 26** — Visualizações | Visual certo: linha = tempo; colunas = comparação; cartão = número-chave; dispersão = relação. Segmentação de dados; hierarquia visual. | Página 1 "Panorama": 3 cartões (IPCA 12m atual, Selic atual, juro real), linha IPCA 12m x Selic, colunas com o varejo por ano e segmentação por ano. Usar a "Monitor 2026" como referência. | Página 1 funcional e legível. |
| [ ] | **Dia 27** — Introdução ao DAX | Coluna calculada x medida; SUM, AVERAGE, MIN, MAX, DIVIDE, COUNTROWS e CALCULATE com filtro simples. | Medidas: IPCA médio, Selic média, Juro real médio, Meses acima de 0,5% = `CALCULATE(COUNTROWS(base), base[ipca_mensal] > 0.5)` e Variação do varejo. Usar nos cartões. | 5 medidas corretas, conferidas com os valores do Python/SQL. |
| [ ] | **Dia 28** — Dashboard e storytelling | Contar uma história com dados: pergunta, contexto, achado e implicação; títulos-conclusão. Reler os slides "Dos conceitos aos indicadores" (TPAE II). | Página 2 "Juros e consumo": dispersão Selic defasada x varejo, caixa de texto com 3 achados e nota de fontes. Ajustar cores, alinhamento e consistência. | Dashboard de 2 páginas pronto. |
| [ ] | **Dia 29** — Documentação e portfólio | O que um recrutador procura: problema, dados, método, resultados e limitações. Estrutura de um README (inspire-se no Plano de dados). | Criar o repositório `analise-macro-brasil` no GitHub com README, notebook, `consultas.sql`, prints do dashboard e dicionário de variáveis. Rascunhar um post para o LinkedIn. | Projeto publicado com README completo. |
| [ ] | **Dia 30** — Avaliação final | Reler o diário dos 30 dias. | Fazer a Avaliação Final: apresentar o dashboard em 3 minutos (grave no celular), responder às perguntas de entrevista, preencher a autoavaliação e definir o próximo ciclo de 30 dias. | Autoavaliação concluída e próximos passos definidos. |

### Avaliação final — Power BI e projeto (Dia 30)

**Exercícios**
- [ ] **Apresentação:** mostre o dashboard em 3 minutos — pergunta, dados, 3 achados e 1 limitação.
- [ ] **Entrevista simulada:** "Qual a diferença entre medida e coluna calculada?", "Por que usar uma tabela calendário?" e "Como você garante que os dados estão corretos?"
- [ ] **Atualização:** clique em "Atualizar" e confira se tudo continua funcionando.

**Critérios de conclusão**
- [ ] Tratamento feito no Power Query, sem ajustes manuais fora dele
- [ ] Pelo menos 1 relacionamento correto com a tabela calendário
- [ ] Pelo menos 4 medidas DAX conferidas com Python ou SQL
- [ ] Dashboard compreensível em 5 segundos (títulos, filtros e fontes visíveis)
- [ ] README publicado no GitHub

### Autoavaliação (notas de 1 a 5)

| Competência | Nota no Dia 1 | Nota no Dia 30 | O que reforçar |
|---|---|---|---|
| Planilhas | | | |
| SQL | | | |
| Lógica de programação (Python) | | | |
| Pandas | | | |
| Estatística aplicada | | | |
| Power BI e DAX | | | |
| Comunicação de resultados | | | |
