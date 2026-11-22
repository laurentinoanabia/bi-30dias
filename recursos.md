# Recursos por semana

Prioridade para conteúdos gratuitos e em português; os materiais em inglês entram quando são claramente os melhores para praticar (SQLBolt, Kaggle, StatQuest).

**Não tente usar todos:** escolha um material principal por semana (marcado com ⭐) e use os outros só para tirar dúvidas.

---

## Fontes de dados (todas as semanas)

| Fonte | Uso no projeto | Link |
|---|---|---|
| Banco Central — SGS | Consultar séries temporais | https://www3.bcb.gov.br/sgspub |
| API do BCB — IPCA mensal (série 433, CSV) | Dias 1, 19 | https://api.bcb.gov.br/dados/serie/bcdata.sgs.433/dados?formato=csv |
| API do BCB — Selic acumulada no mês anualizada (série 4189, CSV) | Dias 3, 19 | https://api.bcb.gov.br/dados/serie/bcdata.sgs.4189/dados?formato=csv |
| IBGE — SIDRA (tabelas da PMC e do IPCA) | Dia 12 (varejo) | https://sidra.ibge.gov.br |
| IBGE — Pesquisa Mensal de Comércio (PMC) | Metodologia do varejo | https://www.ibge.gov.br/estatisticas/economicas/comercio/9227-pesquisa-mensal-de-comercio.html |
| IBGE — IPCA | Conferir o IPCA 12m oficial (Dia 5) | https://www.ibge.gov.br/estatisticas/economicas/precos-e-custos/9256-indice-nacional-de-precos-ao-consumidor-amplo.html |
| Banco Central — histórico das taxas de juros (Copom) | Contexto da Selic | https://www.bcb.gov.br/controleinflacao/historicotaxasjuros |
| Ipeadata — séries macroeconômicas | Extensões futuras | https://www.ipeadata.gov.br |

> Dica do Dia 19: as APIs do BCB leem direto no Pandas com `pd.read_csv(url, sep=";", decimal=",")`.

---

## Semana 1 — Planilhas e estatística descritiva

| Material | Idioma | Link |
|---|---|---|
| ⭐ Fundação Bradesco — Escola Virtual (cursos gratuitos de Excel, com certificado) | PT | https://www.ev.org.br |
| Google — lista oficial de funções do Planilhas | PT | https://support.google.com/docs/table/25273?hl=pt-BR |
| Microsoft — suporte e treinamentos de Excel | PT | https://support.microsoft.com/pt-br/excel |
| Hashtag Treinamentos — aulas de Excel no YouTube | PT | https://www.youtube.com/@HashtagTreinamentos |
| Khan Academy — Estatística e probabilidade | PT | https://pt.khanacademy.org/math/statistics-probability |

**Seus materiais nesta semana**
- **Planilha "Monitor 2026" (Sala de Ações)** — Drive › Compartilhados comigo (somente leitura). Faça uma cópia e estude a estrutura (painel geral, abas por setor, retornos na semana/mês/ano). Extra: recriar com tabela dinâmica o retorno por setor. *Dias 6–7.*
- **Slides "Aula 4 — Dos conceitos aos indicadores" (TPAE II)** — Drive. Use para escrever a pergunta do projeto. *Dia 1.*
- **Documento "Análise de balanço"** — Drive. Margens bruta, operacional e líquida e EBIT como exercício extra de fórmulas. *Opcional.*
- **E-mail "Link das aulas" do curso de Finanças Pessoais (set/2026)** — Gmail. Aulas sobre juros compostos e inflação para reforçar o IPCA acumulado e o juro real. *Dia 5, opcional.*
- **Turmas de Estatística Econômica I e II** — avisos no Gmail; material na turma virtual do SIGAA. Listas e notas de aula para reforçar média, variância e desvio padrão.

---

## Semana 2 — SQL

| Material | Idioma | Link |
|---|---|---|
| ⭐ SQLBolt — lições interativas | EN | https://sqlbolt.com |
| SQLite Online — rodar SQL no navegador, sem instalar nada | — | https://sqliteonline.com |
| DB Browser for SQLite — alternativa para instalar no computador | — | https://sqlitebrowser.org |
| W3Schools — referência rápida de SQL | EN | https://www.w3schools.com/sql/ |
| Kaggle Learn — Intro to SQL (opcional) | EN | https://www.kaggle.com/learn/intro-to-sql |
| SQLZoo — exercícios extras | EN | https://sqlzoo.net |

**Lições do SQLBolt por dia:** Dia 8 → 1–2 · Dia 9 → 3–4 · Dia 10 → 10–11 · Dia 11 → 12 · Dia 12 → 6–7

**Seus materiais nesta semana**
- **"Entrega 4 — Plano de dados" (TPAE II)** — Drive. Parte sobre chaves de junção. *Dia 12.*

---

## Semana 3 — Python, Pandas e correlação

| Material | Idioma | Link |
|---|---|---|
| ⭐ Curso em Vídeo — Python 3, Mundo 1 (ideal para quem começa do zero) | PT | https://www.cursoemvideo.com |
| Tutorial oficial do Python em português | PT | https://docs.python.org/pt-br/3/tutorial/ |
| Python Brasil — introdução e materiais | PT | https://python.org.br/introducao/ |
| Google Colab — programar no navegador | — | https://colab.research.google.com |
| Kaggle Learn — Python | EN | https://www.kaggle.com/learn/python |
| Kaggle Learn — Pandas | EN | https://www.kaggle.com/learn/pandas |
| Pandas — tutoriais oficiais de introdução | EN | https://pandas.pydata.org/docs/getting_started/intro_tutorials/index.html |
| StatQuest — estatística explicada visualmente (Dia 21) | EN | https://www.youtube.com/@statquest |

**Seus materiais nesta semana**
- **Notebooks do Colab da disciplina (aula08 e task07)** — Drive › Colab Notebooks. Referência de sintaxe Python/Pandas já vista em aula; tente refazer trechos sem olhar e compare. *Dias 15, 19 e 20.*
- **Turmas de Estatística Econômica I e II** — SIGAA. Reforço de correlação. *Dia 21.*

---

## Semana 4 — Power BI e portfólio

| Material | Idioma | Link |
|---|---|---|
| ⭐ Microsoft Learn — trilhas gratuitas de Power BI | PT | https://learn.microsoft.com/pt-br/training/powerplatform/power-bi |
| Documentação do Power BI | PT | https://learn.microsoft.com/pt-br/power-bi/ |
| Documentação do Power Query | PT | https://learn.microsoft.com/pt-br/power-query/ |
| Referência de funções DAX | PT | https://learn.microsoft.com/pt-br/dax/ |
| Download do Power BI Desktop (Windows) | PT | https://powerbi.microsoft.com/pt-br/desktop/ |
| Looker Studio — alternativa no navegador para Mac/Chromebook | — | https://lookerstudio.google.com |
| GitHub Docs — primeiro repositório (Dia 29) | PT | https://docs.github.com/pt/get-started/start-your-journey/hello-world |

**Seus materiais nesta semana**
- **Planilha "Monitor 2026"** — referência de painel real. *Dia 26.*
- **Slides "Aula 4 — Dos conceitos aos indicadores" (TPAE II)** — títulos-conclusão do dashboard. *Dia 28.*
- **"Entrega 4 — Plano de dados" (TPAE II)** — dicionário de variáveis para o README. *Dia 29.*

---

## Depois dos 30 dias

- **Dados abertos da CVM** — segundo projeto (indicadores de empresas listadas, com o material de "Análise de balanço"): https://dados.cvm.gov.br
- **Formulário "Educação financeira entre estudantes de graduação" (TPAE II)** — Drive. As respostas anonimizadas podem virar outro projeto (limpeza em Pandas + dashboard), respeitando a LGPD e as regras do projeto.
- **Certificação PL-300** (Microsoft Power BI Data Analyst) — meta de médio prazo.
