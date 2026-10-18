* O **[Capítulo 1 (Introdução)](file:///c:/Users/Luis%20Maia/Documents/TCC2/REPOSITORIO/capitulos/01_introducao.tex)** concentra atualmente **5 figuras**, deixando o início denso visualmente.
* Em contrapartida, o **[Capítulo 3 (Metodologia)](file:///c:/Users/Luis%20Maia/Documents/TCC2/REPOSITORIO/capitulos/03_metodologia.tex)**, o **[Capítulo 4 (Cronograma)](file:///c:/Users/Luis%20Maia/Documents/TCC2/REPOSITORIO/capitulos/04_cronograma.tex)**, o **[Capítulo 5 (Resultados)](file:///c:/Users/Luis%20Maia/Documents/TCC2/REPOSITORIO/capitulos/05_resultados.tex)** e o **[Capítulo 6 (Conclusão)](file:///c:/Users/Luis%20Maia/Documents/TCC2/REPOSITORIO/capitulos/06_conclusao.tex)** possuem **zero figuras**, dependendo exclusivamente de tabelas e texto puro.
* Há inclusive uma imagem já existente no repositório que ainda não foi incorporada ao texto: [`figura_7_githubactionsdeploy.png`](file:///c:/Users/Luis%20Maia/Documents/TCC2/REPOSITORIO/assets/figura_7_githubactionsdeploy.png).

A seguir, apresento o **Plano de Propostas de Imagens e Ilustrações**, estruturado por prioridade e capítulo, com título sugerido, justificativa e local de inserção no texto.

---

### 1. Prioridade Alta: Gráficos de Resultados e Fluxo Metodológico (Impacto Direto na Banca)

São imagens que transformam dados tabulares complexos em percepção visual imediata, indispensáveis para um trabalho de engenharia.

| ID | Título Proposto | Local de Inserção | Justificativa / Descrição do Conteúdo |
| :--- | :--- | :--- | :--- |
| **IMG-01** | **Gráfico Comparativo de Latência Média entre Protocolos (Cenários 1, 2 e 3a)** | [05_resultados.tex:L86](file:///c:/Users/Luis%20Maia/Documents/TCC2/REPOSITORIO/capitulos/05_resultados.tex#L86) (logo após a Seção 5.1.3 / Tabela 3) | Gráfico de barras agrupadas comparando **HTTPS**, **gRPC-Web** e **gRPC Nativo** nos 3 cenários de carga. Evidencia visualmente o *crossover* em que o gRPC reduz a latência pela metade (~4,2s vs ~8,1s no alto volume). |
| **IMG-02** | **Gráfico de Vazão de Dados (*Throughput* em barras/segundo)** | [05_resultados.tex:L86](file:///c:/Users/Luis%20Maia/Documents/TCC2/REPOSITORIO/capitulos/05_resultados.tex#L86) (em conjunto ou logo após IMG-01) | Gráfico de barras comparando a capacidade de entrega de barras/s no Cenário 2 (301 barras) e Cenário 3a (16.865 barras), destacando a vantagem do *server-streaming* gRPC frente à paginação REST. |
| **IMG-03** | **Fluxo Metodológico Ponta a Ponta: da Coleta Externa ao Consumo de Séries Temporais** | [03_metodologia.tex:L26](file:///c:/Users/Luis%20Maia/Documents/TCC2/REPOSITORIO/capitulos/03_metodologia.tex#L26) (final da Seção 3.2 - Questões de Pesquisa) | Diagrama de fluxo de dados mostrando o ciclo completo: Corretora (XP/Rico) $\to$ MT5 $\to$ mt5bridge $\to$ FastAPI (REST) $\to$ TimescaleDB $\to$ Interfaces (gRPC/HTTPS) $\to$ Pesquisadores/Dashboards. Dá ao leitor o mapa mental do sistema. |
| **IMG-04** | **Arquitetura do Procedimento Experimental e *Benchmarking*** | [03_metodologia.tex:L119](file:///c:/Users/Luis%20Maia/Documents/TCC2/REPOSITORIO/capitulos/03_metodologia.tex#L119) (final da Seção 3.7 - Procedimento Experimental) | Diagrama esquemático demonstrando as etapas do experimento: *warmup* de conexões (DNS/TCP/TLS), intercalação das requisições e coleta de métricas nos 3 cenários de volumetria. |

---

### 2. Prioridade Média: Diagramas Técnicos e Conceituais na Fundamentação

Tornam a leitura do Capítulo 2 mais agradável e didática, explicando visualmente padrões de microsserviços, redes e dados.

| ID | Título Proposto | Local de Inserção | Justificativa / Descrição do Conteúdo |
| :--- | :--- | :--- | :--- |
| **IMG-05** | **Comparativo de Comunicação de Rede: HTTP/1.1 (JSON) vs. HTTP/2 com gRPC (Protobuf)** | [02_fundamentacao.tex:L79](file:///c:/Users/Luis%20Maia/Documents/TCC2/REPOSITORIO/capitulos/02_fundamentacao.tex#L79) (Seção 2.6 - Protocolos de Comunicação) | Ilustração didática comparando o modelo de conexões TCP seriais e payloads de texto do REST tradicional contra a multiplexação em canal único e mensagens binárias do gRPC. |
| **IMG-06** | **Mecanismo de Particionamento Temporal em *Chunks* de uma *Hypertable* no TimescaleDB** | [02_fundamentacao.tex:L87](file:///c:/Users/Luis%20Maia/Documents/TCC2/REPOSITORIO/capitulos/02_fundamentacao.tex#L87) (Seção 2.7 - TimescaleDB) | Diagrama mostrando a abstração da *hypertable* particionada dinamicamente por tempo em múltiplos *chunks* físicos de banco de dados, facilitando a compreensão de consultas com `time_bucket`. |
| **IMG-07** | **Arquitetura de Execução do MT5 *Headless* via Camada Wine em Contêiner Linux** | [02_fundamentacao.tex:L63](file:///c:/Users/Luis%20Maia/Documents/TCC2/REPOSITORIO/capitulos/02_fundamentacao.tex#L63) (Subseção 2.4.1 - Wine) | Diagrama em camadas: SO Hospedeiro Linux $\to$ Docker Container $\to$ Wine (tradução de chamadas Win32 para POSIX) $\to$ Terminal MT5 $\to$ Script bridge. |
| **IMG-08** | **Fluxo de Ingestão com Garantia de Idempotência via *Upsert*** | [02_fundamentacao.tex:L103](file:///c:/Users/Luis%20Maia/Documents/TCC2/REPOSITORIO/capitulos/02_fundamentacao.tex#L103) (Seção 2.9 - Estratégia de Upsert) | Fluxograma conceitual demonstrando a chegada de uma barra financeira: validação da chave temporal composta $\to$ decisão entre `INSERT` ou `UPDATE` atômico $\to$ integridade garantida sem duplicidade. |
| **IMG-09** | **Fluxo de Autenticação e Verificação Criptográfica *Stateless* com JWT e Supabase** | [02_fundamentacao.tex:L111](file:///c:/Users/Luis%20Maia/Documents/TCC2/REPOSITORIO/capitulos/02_fundamentacao.tex#L111) (Seção 2.10 - Autenticação com JWT) | Diagrama de sequência entre Pesquisador, Supabase e qData: obtenção do token assinado assimetricamente e validação de permissões diretamente pelo microsserviço sem consulta ao banco a cada requisição. |
| **IMG-10** | **Pipeline de Integração Contínua e *Deploy* Automatizado no GitHub Actions** | [02_fundamentacao.tex:L121](file:///c:/Users/Luis%20Maia/Documents/TCC2/REPOSITORIO/capitulos/02_fundamentacao.tex#L121) (Seção 2.11 - Integração Contínua) | Aproveitamento ou enriquecimento da imagem já existente [`figura_7_githubactionsdeploy.png`](file:///c:/Users/Luis%20Maia/Documents/TCC2/REPOSITORIO/assets/figura_7_githubactionsdeploy.png) para ilustrar o processo de validação de testes e automação. |

---

### 3. Prioridade Estratégica: Governança, Conformidade e Futuro

Reforçam o rigor profissional do projeto e sua expansão organizacional.

| ID | Título Proposto | Local de Inserção | Justificativa / Descrição do Conteúdo |
| :--- | :--- | :--- | :--- |
| **IMG-11** | **Matriz de Fronteira Regulatória e Governança de Dados Financeiros (B3 vs. LTI)** | [03_metodologia.tex:L167](file:///c:/Users/Luis%20Maia/Documents/TCC2/REPOSITORIO/capitulos/03_metodologia.tex#L167) (Subseção 3.9.2 - *Delayed Market Data*) | Diagrama de blocos demonstrando a divisão entre dados *real-time* (uso interno institucional restrito) e a barreira planejada de defasagem (mínimo de 15 minutos) para fins acadêmicos e educacionais. |
| **IMG-12** | **Linha do Tempo Visual das Fases do Projeto (Roadmap 2026)** | [04_cronograma.tex:L41](file:///c:/Users/Luis%20Maia/Documents/TCC2/REPOSITORIO/capitulos/04_cronograma.tex#L41) (acompanhando a Tabela 1) | Um gráfico visual de cronograma/Gantt simplificado ilustrando a evolução temporal dos marcos de 02/Fev a 11/Dez de 2026, tornando o capítulo visualmente atrativo. |
| **IMG-13** | **Topologia de Infraestrutura em Produção no Laboratório (Traefik e Bitwarden)** | [05_resultados.tex:L108](file:///c:/Users/Luis%20Maia/Documents/TCC2/REPOSITORIO/capitulos/05_resultados.tex#L108) (Subseção 5.2.2 - Impactos Organizacionais) | Diagrama da infraestrutura instalada no servidor físico do LTI: roteamento e terminação TLS com Traefik, cofre Bitwarden e redes Docker isoladas. |
| **IMG-14** | **Topologia Futura de Segurança *Zero-Trust* via Malha VPN (Tailscale/WireGuard)** | [06_conclusao.tex:L65](file:///c:/Users/Luis%20Maia/Documents/TCC2/REPOSITORIO/capitulos/06_conclusao.tex#L65) (Subseção 6.4.2 - Pilar de Arquitetura e Rede) | Ilustração mostrando o fechamento das portas públicas da internet e a comunicação restrita aos nós de pesquisa por meio da rede privada em malha criptografada. |

