# Prompt: Inserir as imagens IMG-01 a IMG-14 no TCC

## Contexto
Projeto LaTeX do TCC em `c:\Users\Luis Maia\Documents\TCC2\REPOSITORIO`. Capítulos em `capitulos/*.tex`. As 14 imagens já estão em `assets/` com os nomes `IMG-01.jpg` … `IMG-14.jpg`. O plano completo está em `assets/plan_new_images.md` (leia-o primeiro; ele é a fonte de verdade para título e local).

## Tarefa
Para cada imagem, insira um ambiente `figure` no local indicado, **sem alterar nenhum texto existente** (preserve comentários e conteúdo não relacionado).

### Padrão obrigatório (igual ao já usado em `capitulos/01_introducao.tex`)
```latex
\begin{figure}[htb]
    \centering
    \caption{<Título proposto>.}
    \includegraphics[width=\textwidth]{assets/IMG-XX.jpg}
    \label{fig:<slug_curto>}
\end{figure}
```
- Legenda ABNT: `\caption` antes de `\includegraphics`. Se o projeto exigir fonte, adicione `\fonte{Elaborado pelo autor.}` conforme usado nas demais figuras (verifique).
- Insira ao final do parágrafo/seção indicado, com linha em branco antes e depois.
- Use `\label` único e descritivo (ex.: `fig:latencia_protocolos`).
- Adicione uma referência no texto (`Conforme a Figura~\ref{fig:...}`) apenas se houver frase natural para isso; não reescreva parágrafos.
- Escrita impessoal (sem primeira pessoa).

## Mapeamento imagem → local

| Imagem | Arquivo destino (referência) | Local | Título (caption) |
| :--- | :--- | :--- | :--- |
| IMG-01 | `capitulos/05_resultados.tex` ~L86 | Após Seção 5.1.3 / Tabela 3 | Comparativo de latência média entre protocolos (Cenários 1, 2 e 3a) |
| IMG-02 | `capitulos/05_resultados.tex` ~L86 | Logo após IMG-01 | Vazão de dados (\textit{throughput}) em barras por segundo |
| IMG-03 | `capitulos/03_metodologia.tex` ~L26 | Final da Seção 3.2 (Questões de Pesquisa) | Fluxo metodológico ponta a ponta: da coleta externa ao consumo de séries temporais |
| IMG-04 | `capitulos/03_metodologia.tex` ~L119 | Final da Seção 3.7 (Procedimento Experimental) | Arquitetura do procedimento experimental e \textit{benchmarking} |
| IMG-05 | `capitulos/02_fundamentacao.tex` ~L79 | Seção 2.6 (Protocolos de Comunicação) | HTTP/1.1 (JSON) versus HTTP/2 com gRPC (Protobuf) |
| IMG-06 | `capitulos/02_fundamentacao.tex` ~L87 | Seção 2.7 (TimescaleDB) | Particionamento temporal em \textit{chunks} de uma \textit{hypertable} |
| IMG-07 | `capitulos/02_fundamentacao.tex` ~L63 | Subseção 2.4.1 (Wine) | Execução do MT5 \textit{headless} via Wine em contêiner Linux |
| IMG-08 | `capitulos/02_fundamentacao.tex` ~L103 | Seção 2.9 (Estratégia de Upsert) | Fluxo de ingestão com idempotência via \textit{Upsert} |
| IMG-09 | `capitulos/02_fundamentacao.tex` ~L111 | Seção 2.10 (Autenticação com JWT) | Autenticação e verificação criptográfica \textit{stateless} com JWT e Supabase |
| IMG-10 | `capitulos/02_fundamentacao.tex` ~L121 | Seção 2.11 (Integração Contínua) | Pipeline de integração contínua e \textit{deploy} automatizado no GitHub Actions |
| IMG-11 | `capitulos/03_metodologia.tex` ~L167 | Subseção 3.9.2 (\textit{Delayed Market Data}) | Fronteira regulatória e governança de dados financeiros (B3 versus LTI) |
| IMG-12 | `capitulos/04_cronograma.tex` ~L41 | Junto à Tabela 1 | Linha do tempo das fases do projeto (\textit{roadmap} 2026) |
| IMG-13 | `capitulos/05_resultados.tex` ~L108 | Subseção 5.2.2 (Impactos Organizacionais) | Topologia da infraestrutura em produção no laboratório (Traefik e Bitwarden) |
| IMG-14 | `capitulos/06_conclusao.tex` ~L65 | Subseção 6.4.2 (Pilar de Arquitetura e Rede) | Topologia futura de segurança \textit{zero-trust} via malha VPN (Tailscale/WireGuard) |

## Regras importantes
1. **Os números de linha são aproximados**: as inserções anteriores deslocam as linhas. Localize cada ponto pelo **título da seção/subseção**, não pelo número. Dica: processe cada arquivo de baixo para cima, ou releia o arquivo entre edições.
2. Faça todas as edições de um mesmo arquivo `.tex` numa única operação quando possível.
3. IMG-10: **não remova** `figura_7_githubactionsdeploy.png` se já estiver referenciada; apenas verifique se já existe figura na Seção 2.11. Se existir, insira IMG-10 logo após ela (ou substitua somente se eu confirmar).
4. Confirme que cada `assets/IMG-XX.jpg` existe antes de referenciá-lo; reporte os ausentes.
5. Não crie `\label` duplicados (busque `\label{fig:` antes).
6. Se a compilação LaTeX estiver disponível, compile e relate erros/avisos de figuras não encontradas ou `Overfull`/flutuantes muito distantes.

## Entrega
Ao final, liste em uma tabela: imagem, arquivo `.tex`, linha onde foi inserida, `\label` usado, e quaisquer pendências ou ambiguidades.
