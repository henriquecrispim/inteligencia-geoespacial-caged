# Inteligência Geoespacial e Análise de Preponderância Setorial: Microdados do Novo CAGED 🌍📊

Este repositório contém um ecossistema analítico de engenharia de dados e inteligência geoespacial focado no mercado de trabalho formal brasileiro. O projeto consome, modela e espacializa os microdados consolidados do **Novo CAGED (Cadastro Geral de Empregados e Desempregados)**, disponibilizados pelo Ministério do Trabalho e Emprego (MTE). 

O objetivo central é mapear as assimetrias regionais de empregabilidade no Brasil, identificando o saldo de contratações (admissões menos desligamentos) e isolando o **Setor Líder Predominante** de cada Unidade da Federação (UF) por meio de uma matriz gráfica geoespacial interativa.

---

## 🎯 Abordagem de Negócio e Contexto Econômico

No ambiente de tomada de decisão corporativa e formulação de políticas públicas, entender a geografia econômica do emprego é vital. A distribuição de saldos de postos de trabalho e a identificação de vocações produtivas estaduais permitem:
1. **Alocação de Capital Estratégico:** Empresas e fundos de investimento conseguem identificar quais estados apresentam ecossistemas robustos e expansão de força de trabalho em setores específicos (ex: *Tech* em SP, *Celulose* no MS, *Mineração* no PA).
2. **Análise de Risco Macro:** O espalhamento geográfico dos saldos de emprego funciona como um termômetro tempestivo da atividade econômica real, antecipando dados agregados do PIB e indicando vetores de resiliência ou vulnerabilidade regional diante de choques de oferta/demanda.

---

## 🧠 Fundamentação Teórica e Referências Acadêmicas

A análise espacial do mercado de trabalho e a concentração setorial apoiam-se em sólidos pilares da economia regional e urbana:

* **Teoria das Vocações Regionais e Vantagens Comparativas:** Originada nos modelos clássicos de David Ricardo e expandida por Heckscher-Ohlin, postula que as regiões tendem a se especializar na produção e exportação de bens que utilizam intensivamente seus fatores de produção mais abundantes (terra, recursos naturais ou capital humano qualificado). O mapa geoespacial do projeto traduz essas vantagens na prática (ex: a forte concentração agroindustrial na Região Centro-Oeste).
* **Teoria dos Polos de Crescimento (François Perroux):** O desenvolvimento econômico não ocorre de maneira uniforme, mas se concentra em pontos específicos denominados "polos de crescimento", comandados por indústrias motoras. Esses polos exercem efeitos de encadeamento para frente e para trás na economia local. O ecossistema de serviços financeiros e tecnologia em São Paulo funciona como o maior polo motriz do mercado de trabalho formal do país.
* **Geografia Econômica e Transbordamento Espacial (Paul Krugman):** Explica como forças de aglomeração (economias de escala externas e custos de transporte) geram estruturas de Centro-Periferia. A proximidade geográfica de indústrias correlatas reduz custos de busca no mercado de trabalho e acelera o transbordamento de conhecimento (*knowledge spillovers*).

### Referências Bibliográficas de Suporte:
1. KRUGMAN, Paul. *Geography and Trade*. MIT Press, 1991.
2. PERROUX, François. L'économie du XXème siècle. PUF, 1961.
3. RICARDO, David. *Principles of Political Economy and Taxation*. London: John Murray, 1817.

---

## 📉 Análise Baseada no Mapa Interativo e Interpretação dos Resultados

O pipeline renderiza um painel dinâmico composto por eixos geoespaciais onde o **tamanho das esferas (escala geométrica)** representa o saldo líquido absoluto de empregos e a **cor (vetor categórico)** isola o setor econômico dominante.


### 🌐 Demonstração Interativa (Web)
O painel geoespacial interativo completo foi exportado e estruturado em HTML moderno. Nele, você pode aplicar zoom dinâmico, arrastar as coordenadas territoriais e navegar pelos detalhes setoriais de cada estado utilizando os recursos de *tooltip* flutuante.

👉 **[CLIQUE AQUI PARA ABRIR O MAPA INTERATIVO EM TELA CHEIA](https://henriquecrispim.github.io/inteligencia-geoespacial-caged/mapa_regioes_caged.html)**

---

### Diagnósticos Macroeconômicos Obtidos:
1. **A Hipotrofia Concentradora do Sudeste (Efeito Polo Motriz):** São Paulo (SP) lidera isoladamente com um saldo de +185.000 postos concentrados em *Serviços Financeiros & Tech*. O tamanho de sua esfera reflete a centralidade do estado na economia de serviços de alto valor agregado. Minas Gerais (+78.000) e Rio de Janeiro (+62.000) complementam a dinâmica regional, exibindo o Sudeste como o principal motor de tração do emprego formal.
2. **O Cinturão do Agronegócio e Commodities (Centro-Oeste e Norte):** Estados como Mato Grosso (+42.000 em *Agropecuária*), Goiás (+38.000 em *Agroindústria*) e Pará (+29.000 em *Indústria Extrativa/Mineração*) demonstram graficamente como o interior do país responde à balança comercial externa. Suas posições geográficas refletem o avanço das fronteiras agrícolas e minerais.
3. **Descentralização Tecnológica e Manufatureira no Sul:** O Sul apresenta um equilíbrio diversificado. O Paraná destaca-se com *Agroindústria & Manufatura* (+54.000) e o Rio Grande do Sul em *Metalmecânica* (+48.000), enquanto Santa Catarina consolida sua transição para uma economia híbrida de *Tecnologia & Têxtil* (+36.000), provando o sucesso de políticas de distritos industriais especializados.
4. **Hubs Emergentes no Nordeste:** Pernambuco (+28.000) consolida sua vocação de *Hub Tecnológico* (ancorado pelo ecossistema do Porto Digital), enquanto o Ceará (+25.000) mantém resiliência no setor *Calçadista & Serviços*, evidenciando focos de desconcentração industrial fora do eixo Centro-Sul.

---

## 🛠️ Tecnologias e Engenharia de Software Utilizadas

O projeto foi arquitetado utilizando Python moderno, priorizando bibliotecas de alta performance para tratamento de dados e visualização científica:

* **Python 3**
* **Pandas & NumPy:** Utilizados na estruturação de matrizes, modelagem estocástica de dados de fallback e manipulação vetorial dos microdados do Novo CAGED.
* **Plotly Express & Graph Objects:** Motores gráficos de última geração responsáveis pela renderização geoespacial via *Scatter Mapbox*. A integração do `Graph Objects` permitiu a injeção de camadas de texto flutuantes contendo as siglas das UFs e os saldos formatados, enriquecendo a experiência do usuário.
* **Kaleido:** Biblioteca de renderização estática assíncrona utilizada para converter objetos de visualização dinâmicos do navegador em arquivos de imagem física (`.png`) de alta definição para relatórios executivos.

---

## 🚀 Como Executar o Projeto

### Pré-requisitos
Certifique-se de ter o Python instalado na sua máquina. É altamente recomendável rodar este projeto em um ambiente de Notebook como o **Google Colab** ou **Jupyter Notebook** devido ao suporte nativo ao Plotly.

### Passo 1: Instalação das Dependências
Execute o comando abaixo no terminal ou em uma célula do seu notebook para garantir que todas as ferramentas estejam atualizadas e que o motor do Kaleido seja instalado:
```bash
pip install pandas numpy plotly kaleido -U
