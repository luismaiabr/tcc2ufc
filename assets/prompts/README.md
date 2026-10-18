# Índice de prompts de ilustrações

Prompts de geração de imagem para as ilustrações planejadas em [plan_new_images.md](../plan_new_images.md). Cada arquivo é autossuficiente (contexto + descrição + estilo + especificações + restrições) e contém apenas o texto do prompt.

| Nº | Arquivo | Título da ilustração | Figura / Seção do TCC |
| :-- | :-- | :-- | :-- |
| 01 | [01_grafico-latencia-media-protocolos.md](01_grafico-latencia-media-protocolos.md) | Gráfico comparativo de latência média entre protocolos (Cenários 1, 2 e 3a) | IMG-01 — Cap. 5, Seção 5.1.3 (`05_resultados.tex`, L86) |
| 02 | [02_grafico-vazao-throughput.md](02_grafico-vazao-throughput.md) | Gráfico de vazão de dados (throughput em barras/segundo) | IMG-02 — Cap. 5, Seção 5.1.3 (`05_resultados.tex`, L86) |
| 03 | [03_fluxo-metodologico-ponta-a-ponta.md](03_fluxo-metodologico-ponta-a-ponta.md) | Fluxo metodológico ponta a ponta: da coleta externa ao consumo de séries temporais | IMG-03 — Cap. 3, Seção 3.2 (`03_metodologia.tex`, L26) |
| 04 | [04_procedimento-experimental-benchmarking.md](04_procedimento-experimental-benchmarking.md) | Arquitetura do procedimento experimental e benchmarking | IMG-04 — Cap. 3, Seção 3.7 (`03_metodologia.tex`, L119) |
| 05 | [05_comparativo-http1-json-vs-http2-grpc.md](05_comparativo-http1-json-vs-http2-grpc.md) | Comparativo de comunicação de rede: HTTP/1.1 (JSON) vs. HTTP/2 com gRPC (Protobuf) | IMG-05 — Cap. 2, Seção 2.6 (`02_fundamentacao.tex`, L79) |
| 06 | [06_particionamento-hypertable-chunks.md](06_particionamento-hypertable-chunks.md) | Particionamento temporal em chunks de uma hypertable no TimescaleDB | IMG-06 — Cap. 2, Seção 2.7 (`02_fundamentacao.tex`, L87) |
| 07 | [07_mt5-headless-wine-conteiner.md](07_mt5-headless-wine-conteiner.md) | Arquitetura de execução do MT5 headless via Wine em contêiner Linux | IMG-07 — Cap. 2, Subseção 2.4.1 (`02_fundamentacao.tex`, L63) |
| 08 | [08_ingestao-idempotente-upsert.md](08_ingestao-idempotente-upsert.md) | Fluxo de ingestão com garantia de idempotência via upsert | IMG-08 — Cap. 2, Seção 2.9 (`02_fundamentacao.tex`, L103) |
| 09 | [09_autenticacao-jwt-supabase.md](09_autenticacao-jwt-supabase.md) | Fluxo de autenticação e verificação criptográfica stateless com JWT e Supabase | IMG-09 — Cap. 2, Seção 2.10 (`02_fundamentacao.tex`, L111) |
| 10 | [10_pipeline-ci-cd-github-actions.md](10_pipeline-ci-cd-github-actions.md) | Pipeline de integração contínua e deploy automatizado no GitHub Actions | IMG-10 — Cap. 2, Seção 2.11 (`02_fundamentacao.tex`, L121) |
| 11 | [11_fronteira-regulatoria-delayed-market-data.md](11_fronteira-regulatoria-delayed-market-data.md) | Matriz de fronteira regulatória e governança de dados financeiros (B3 vs. LTI) | IMG-11 — Cap. 3, Subseção 3.9.2 (`03_metodologia.tex`, L167) |
| 12 | [12_linha-do-tempo-cronograma-2026.md](12_linha-do-tempo-cronograma-2026.md) | Linha do tempo visual das fases do projeto (Roadmap 2026) | IMG-12 — Cap. 4, Tabela 1 (`04_cronograma.tex`, L41) |
| 13 | [13_topologia-producao-traefik-bitwarden.md](13_topologia-producao-traefik-bitwarden.md) | Topologia de infraestrutura em produção no laboratório (Traefik e Bitwarden) | IMG-13 — Cap. 5, Subseção 5.2.2 (`05_resultados.tex`, L108) |
| 14 | [14_topologia-futura-zero-trust-vpn.md](14_topologia-futura-zero-trust-vpn.md) | Topologia futura de segurança Zero Trust via malha VPN (Tailscale/WireGuard) | IMG-14 — Cap. 6, Subseção 6.4.2 (`06_conclusao.tex`, L65) |

## Padrão visual comum

Diagrama vetorial plano em fundo branco; paleta #1F3A5F, #2E6FBF, #DCE8F7, #1A9E8F, #E8833A, #5B6770, #EEF2F6 (e #C0392B apenas para bloqueios); tipografia sans-serif geométrica (Inter/Helvetica); contornos de 2 px e setas de 2,5 px.

## Decisões de interpretação

- **Sem prompts anteriores:** `assets/prompts/` só continha `prompt_to_create_prompts.md`; o estilo foi definido do zero e repetido em todos os arquivos.
- **IMG-01/02:** valores numéricos extraídos das tabelas de `05_resultados.tex` (Cenário 1: 45,2 / 38,5 / 30,1 ms; Cenário 2 e 3a: tabelas agregadas). O Cenário 1 não possui throughput, por isso IMG-02 cobre só os Cenários 2 e 3a, como no plano.
- **IMG-04:** itens de métricas (latência média, percentis 95/99, throughput, taxa de erro) vêm das tabelas de resultados.
- **IMG-06:** chunks usam rótulos genéricos de intervalo, sem datas inventadas.
- **IMG-09:** assumiu-se que o qData valida o token com a chave pública do emissor (assinatura assimétrica, conforme o plano); detalhes como JWKS não foram representados.
- **IMG-10:** em vez de reaproveitar `figura_7_githubactionsdeploy.png`, o prompt gera um pipeline novo, baseado na Seção 3 (testes de unidade/integração, análise estática, code review, promoção a produção). Nota: o texto da metodologia diz que os testes de CI são propostas ainda não implementadas; avalie se a figura deve sinalizar isso.
- **IMG-11:** a "matriz" do título foi interpretada como diagrama de blocos com barreira de defasagem (mínimo de 15 min), conforme a descrição do plano.
- **IMG-12:** fases e meses extraídos da Tabela 1 de `04_cronograma.tex`; fases de Jul–Ago agrupadas em uma barra única.
- **IMG-13:** a relação "serviços consultam o Bitwarden" e o isolamento entre duas redes Docker são interpretações plausíveis do plano, que cita apenas "redes Docker isoladas".
- **IMG-14:** a figura inclui o selo "planejado", pois a topologia ainda não foi implementada (Cap. 6).
