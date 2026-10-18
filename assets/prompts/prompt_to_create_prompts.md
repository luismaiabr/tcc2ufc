# Papel
Você é um engenheiro de prompts especializado em geração de imagens (texto-para-imagem) para ilustrações acadêmicas e técnicas, usadas em um TCC.
# Tarefa
Leia integralmente o arquivo `assets/plan_new_images.md`. Ele descreve as ilustrações planejadas. Para CADA ilustração listada, crie um prompt de geração de imagem detalhado e pronto para uso.
# Entradas a consultar antes de escrever
1. `assets/plan_new_images.md`: fonte principal. Respeite a descrição, o objetivo e a legenda de cada ilustração.
2. Se o plano citar capítulos ou seções do TCC (`capitulos/*.tex`), consulte-os para manter a terminologia e o tema coerentes.
3. Se existirem prompts anteriores em `assets/prompts`, mantenha a consistência de estilo com eles.
# Saída
- Pasta: `assets/prompts/` (crie-a se não existir).
- UM arquivo `.md` por ilustração, sem agrupar prompts.
- Nome do arquivo: `NN_slug-descritivo.md`, em minúsculas e sem acentos. `NN` é o número sequencial, com dois dígitos, na ordem do plano. Exemplo: `01_arquitetura-geral.md`.
- Ao final, gere também `assets/prompts/README.md` com um índice. Ele deve ter uma tabela com: nº, arquivo, título da ilustração e figura/seção do TCC a que se refere.
# Formato de cada arquivo
O arquivo deve conter APENAS o texto do prompt, bruto, pronto para copiar e colar. Não inclua cabeçalhos, comentários, explicações, metadados nem blocos de código ao redor.
O prompt deve seguir esta estrutura, em texto corrido ou em parágrafos curtos:
1. **Parágrafo de contexto (obrigatório, sempre o primeiro):** descreva o projeto (TCC, tema, público-alvo), a finalidade da imagem no documento e o tom visual geral. Este parágrafo pode ser idêntico em vários prompts. Se for, copie-o integralmente em cada arquivo, porque cada prompt precisa ser autossuficiente.
2. **Descrição da cena/diagrama:** elementos, rótulos e textos exatos que devem aparecer, relações entre os elementos (setas, fluxos, hierarquia), composição e enquadramento.
3. **Estilo visual:** técnica (vetorial, flat, isométrica, diagrama técnico etc.), paleta de cores com códigos HEX, tipografia, espessura de linhas e nível de detalhe.
4. **Especificações técnicas:** proporção (aspect ratio), fundo adequado para impressão acadêmica, alta resolução e legibilidade em tamanho reduzido.
5. **Restrições negativas:** o que evitar, por exemplo texto ilegível ou inventado, marcas d'água, sombras exageradas, elementos decorativos irrelevantes e estilos que não sejam acadêmicos.
# Regras de qualidade
- Seja específico e inequívoco. Evite termos vagos como "bonito" ou "moderno".
- Mantenha um estilo visual consistente entre todas as ilustrações (mesma paleta, tipografia e estética), definindo-o no contexto ou no bloco de estilo.
- Todo texto que deve aparecer na imagem deve estar entre aspas e escrito corretamente em português do Brasil.
- Não invente elementos que o plano não menciona. Se houver ambiguidade, escolha a interpretação mais plausível e liste a decisão no `README.md`.
- Escreva os prompts em português, salvo se o plano indicar outro idioma para a imagem.
- Não altere `assets/plan_new_images.md` nem nenhum outro arquivo existente.
# Verificação final
Confirme que:
- O número de arquivos é igual ao número de ilustrações do plano.
- Cada arquivo começa com o parágrafo de contexto.
- Nenhum arquivo contém nada além do prompt.
- O README lista todos os arquivos.
