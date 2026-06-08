# 🏈 NFL no Brasil: Crescimento que Não Para

Análise estratégica de dados ponta a ponta (End-to-End) que investiga o crescimento do mercado da NFL (National Football League) no Brasil, o perfil de engajamento digital dos fãs, o impacto econômico dos eventos em solo nacional e a performance histórica das franquias e atletas. 

O projeto adota uma arquitetura híbrida de dados para o consumo do relatório, combinando o armazenamento relacional estruturado em banco de dados com fontes de dados ágeis em planilhas para dimensões analíticas complementares.

---

## 🛠️ Stack Tecnológica & Ferramentas
* **Figma:** Prototipagem de UI/UX, arquitetura de wireframes e design de backgrounds/componentes customizados para o dashboard.
* **Python 3 & Pandas:** Engenharia de recursos, tratamento de inconsistências, filtragem, preparação e limpeza de dados.
* **Claude (Anthropic IA):** Co-piloto de inteligência artificial utilizado para acelerar o desenvolvimento, auxiliando na correção ágil de códigos Python, otimização de consultas e estruturação lógica do projeto.
* **SQLAlchemy & Psycopg2:** Conexão nativa e automação da carga de dados para o banco de dados.
* **PostgreSQL:** Armazenamento relacional e gerenciamento de dados de mercado da liga.
* **Excel (.xlsx):** Armazenamento de dados analíticos complementares e dimensões históricas integradas ao modelo.
* **Power BI & DAX:** Modelagem dimensional mista, criação de métricas calculadas de negócio e construção de visuais dinâmicos.

---

## ⚙️ Engenharia de Dados & Arquitetura Híbrida (ETL)

O projeto foi desenhado para equilibrar a robustez de um banco de dados relacional com a flexibilidade de arquivos complementares:

1. **Extração e Tratamento (Python/Pandas):** 
   Os dados brutos passaram por processos de normalização de tipos de dados, consistência de colunas e remoção de redundâncias utilizando Python no Jupyter Notebook. A tabela de fatos `fact_brazil_games` foi isolada e limpa para garantir precisão regulatória.
2. **Carga no Banco (PostgreSQL):** 
   Criação de uma string de conexão via driver `psycopg2` integrada ao SQLAlchemy. O upload da tabela de fatos tratada foi automatizado diretamente através do método `.to_sql()` com a regra `if_exists='append'`.
3. **Modelagem e Integração Mista (Power BI):** 
   Conforme documentado nas configurações de fontes de dados do projeto (referência: `image_a70d42.png`), o ecossistema do relatório consome dados diretamente do servidor local PostgreSQL (`nfl_brasil_db`), cruzando-os eficientemente no Power Query com dimensões estratégicas estruturadas em arquivos locais Excel (como dados de buscas, impacto econômico, dados históricos de franquias e Hall of Fame).

---

## 📊 Análise do Dashboard & Insights de Negócio

O relatório conta com uma seção de KPIs principais unificada no topo de todas as páginas, apresentando números consolidados impressionantes: **45 Milhões de Fãs no Brasil** (+9,8% vs ano anterior), **6 Milhões em Engajamento nas Redes** (+22,5%), **14.3 Milhões em Audiência de Jogos**, **R$ 670M em Receita Estimada** e **95K de Público nos Jogos**.

Abaixo, detalha-se a composição analítica de cada uma das 5 telas do projeto:

### 1. Visão Geral 
Focada em apresentar a evolução macro do esporte no ecossistema brasileiro.
* **Métricas Principais:** Distribuição geográfica de fãs, audiência por meio de transmissão e a linha do tempo de interesse histórico.
* **Insights Chave:**
  * **Concentração de Mercado:** O estado de São Paulo domina de forma absoluta o mercado consumidor da NFL no país com **53,36% dos fãs**, seguido pelo Rio de Janeiro com **27,61%**.
  * **Fenômeno Streaming/Alternativo:** A CazéTV (YouTube BR) consolidou-se como o maior meio de transmissão de audiência no país, saltando de **3,0 Milhões em 2024 para 4,2 Milhões de espectadores em 2025**, superando canais tradicionais de TV fechada e aberta.
  * **Evolução Exponencial:** O interesse do brasileiro saltou de apenas 4,5 milhões de pessoas em 2015 para uma projeção incrível de **24,5 milhões de pessoas em 2025**.

### 2. NFL no Brasil 
Mapeia o impacto comercial e o histórico de eventos oficiais programados para o país.
* **Métricas Principais:** Comparativo de impacto econômico contra eventos tradicionais, relação público vs. capacidade dos estádios e termos de busca.
* **Insights Chave:**
  * **Força Econômica:** O jogo da NFL em São Paulo (Eagles vs Packers) gerou um impacto econômico brutal de **R$ 340 Milhões**, superando eventos tradicionais e históricos da cidade como o Carnaval de São Paulo (R$ 201M) e o Réveillon (R$ 140M).
  * **Geração de Empregos:** O movimento gerou uma média consistente de mais de **12.500 empregos** diretos e indiretos entre os anos de 2024 e 2025.
  * **Expectativa Futura:** A projeção para o *Rio Game 2026* no Maracanã aponta um público esperado de **75K**, aproximando-se do limite máximo de capacidade do estádio (78K).

### 3. Times e Franquias 
Analisa a popularidade e a performance das equipes do ponto de vista do torcedor nacional.
* **Métricas Principais:** Ranking de popularidade de buscas na web, histórico de vitórias em temporada regular e maiores detentores de títulos de Super Bowl.
* **Insights Chave:**
  * **A Maior Torcida:** O **Green Bay Packers** lidera como a maior torcida do país com **12% da preferência**, seguido de perto pelo San Francisco 49ers (11%) e New England Patriots (11%).
  * **Domínio de Engajamento:** Apesar dos Packers terem a maior torcida declarada, o **Kansas City Chiefs lidera o ranking de buscas na web de forma isolada com 415.000 pesquisas**, impulsionado pelo sucesso recente e a presença na mídia de atletas de elite.

### 4. Jogadores e Ícones 
Focado no engajamento gerado pelos maiores astros e o legado histórico dos atletas que conquistaram o público brasileiro.
* **Métricas Principais:** Ranking de jogadores mais populares, detalhamento de recordes e memorial Hall of Fame.
* **Insights Chave:**
  * **Os Rostos da Liga:** Patrick Mahomes (Quarterback) e Travis Kelce (Tight End), ambos do Kansas City Chiefs, são as figuras de maior engajamento e popularidade no cenário brasileiro atual.
  * **Legado Imortal:** Tom Brady é destacado como o grande pilar de expansão internacional, documentado por seus 7 títulos de Super Bowl, 3x MVP e duas décadas de dominância que pavimentaram a base de fãs atual no Brasil.

### 5. Engajamento Digital 
Exibe minuciosamente a expansão das redes sociais e os canais de comunicação com maior tração entre os torcedores.
* **Métricas Principais:** Crescimento de seguidores ano a ano, fatia de participação por plataforma e histórico de redes líderes.
* **Insights Chave:**
  * **Domínio do TikTok:** Embora o Instagram detenha **32% de participação de mercado**, o TikTok desponta como a plataforma que causou a maior disrupção recente, liderando o ganho de novos seguidores a partir de 2021 (alcançando **1.9 Milhão de seguidores totais**).
  * **Retenção de Comunidade:** O Instagram manteve a liderança orgânica absoluta em novos seguidores entre 2016 e 2020, evidenciando a transição do formato de fotos e posts estáticos para vídeos curtos e verticais a partir de 2021 na preferência do fã de futebol americano.

---

## 🎨 Design de Interface & Experiência (UI/UX no Figma)
Para entregar um produto que se distancie de relatórios corporativos frios e genéricos, a interface gráfica foi planejada para simular um aplicativo moderno de streaming ou esportes:
* **Identidade Visual Temática:** Uso da paleta de cores oficial da NFL, utilizando tons profundos de azul (*Navy Blue*), preto de alto contraste e detalhes brilhantes nas métricas para guiar a atenção do usuário (*Scannability*).
* **Performance:** Cards e divisores geométricos desenhados diretamente no Figma e importados como imagem de fundo. Isso otimiza o tempo de renderização do Power BI, reduzindo o consumo de memória do navegador ao evitar a criação de múltiplos formatos nativos na ferramenta.
* **Acessibilidade Visiva:** Fontes limpas e legíveis, amplo espaçamento entre elementos gráficos e uso intuitivo de ícones nos indicadores chaves de performance (KPIs).

---
Desenvolvido por Gabriel Henrique Corrêa Aniceto.

