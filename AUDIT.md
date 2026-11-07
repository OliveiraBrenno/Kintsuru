# Auditoria técnica — Kintsuru

Data: 06/11/2026. Escopo: início, cardápio/pedido e unidades. Skill Impeccable invocada explicitamente; auditoria seguida das correções autorizadas.

## Veredito de integridade

Identidade preservada: escrita de pincel, marinho, coral, papel creme, tsuru, comida e mascote sushi. Conteúdo e controles permanecem HTML editável. O creme do detector vem do mockup aprovado e não indica uma troca de direção necessária.

## Pontuação heurística

| Dimensão | Antes | Após | Evidência |
|---|---:|---:|---|
| Acessibilidade | 2/4 | 3/4 | Recuperação de menu/formulário, alvos e leitura melhorados |
| Desempenho | 2/4 | 3/4 | Hero responsivo e mascotes/logo WebP; origens preservadas |
| Temas/tokens | 3/4 | 3/4 | Paleta vigente; novos tokens de controle e detalhe |
| Responsividade | 2/4 | 4/4 | Textos ampliados e ações passam; filtros e listas usam rolagem nativa |
| Integridade | 3/4 | 4/4 | Pedido, foco, persistência, filtros e demonstração verificados |
| Total | 12/20 | 17/20 | Bom dentro do escopo Chromium testado |

A pontuação é julgamento técnico, não certificação WCAG ou Lighthouse.

## Problemas encontrados e corrigidos

Seis achados consolidados: 0 P0, 1 P1, 5 P2. Todos corrigidos.

| Prioridade e achado | Local / impacto | Alteração e evidência |
|---|---|---|
| P1 — Corte de conteúdo ampliado | `style.css`, links ao cardápio, categorias, descrições e envio do pedido; ensaio a 200% cortava palavras e ação | Quebras naturais, largura mínima flexível, cabeçalhos com refluxo e botões com texto quebrável. Cinco rotas em conjunto passaram no ensaio final. Relacionado ao risco de perda em 1.4.4; não tratado como certificação formal |
| P2 — Alvos pequenos | `.round`, `.nav-toggle`, `.add`, `.filters button`, `.quantity button`, links de rodapé: ações de 28–37 px dificultavam toque | Alvos de 44 px, campos de 48 px. Os rádios nativos seguem visualmente pequenos, mas seus labels clicáveis têm 44 px; a caixa do input isolada não é a área total de ativação. 44 px é o padrão de conforto adotado, não o mínimo geral AA de 2.5.8 |
| P2 — Texto minúsculo | Descrições do cardápio a 11 px, ações e porções a 9–11 px | Descrições e ações a 14 px, títulos de prato mobile a 16 px, informação auxiliar a pelo menos 12 px; sem trocar as famílias. Detector final sem alerta de texto minúsculo |
| P2 — Recuperação incompleta do menu | `app.js`: Escape fechava sem devolver foco; painel não fechava ao clicar fora ou trocar breakpoint | Foco no acionador, fechamento fora do cabeçalho e ao mudar para desktop. Testes aprovados. Filtros também anunciam a quantidade de pratos selecionados |
| P2 — Formulário aceitava espaços | `app.js`, checkout: required sozinho aceita strings de espaços e o erro geral não focava o campo | Custom validity nativa com mensagem específica, limpeza ao editar e endereço sem erro residual ao mudar para retirada. Testes de entrega, retirada, correção e simulação aprovados |
| P2 — Imagens de abertura pesadas | `assets/hero.png`: 2.926.984 bytes; logo e mascotes PNG grandes para a área exibida | Hero WebP de 314.542 bytes em 1536 px e 100.238 bytes em 768 px, com srcset/sizes. Cinco exports de logo/mascotes somam 515.520 bytes; PNGs originais preservados. Unidades fora do destaque com lazy loading/decodificação assíncrona |

## Aspectos preservados

Cálculos monetários em centavos, limite de quantidade, persistência do carrinho, foco após remoção, conteúdo de demonstração, labels nativos, movimento reduzido, paleta e fotos existentes. `npm test` aprovado: totais, entrega, retirada e geração da mensagem. Não foram ativadas integrações externas.

## Verificação e limites

- Chromium real por CDP, com viewport emulado. As cinco rotas dos dois projetos foram capturadas em 320, 390, 760, 1024 e 1440 px: 25 combinações sem overflow horizontal, imagens quebradas ou cortes geométricos encontrados em escala normal.
- Texto a 200% por CSS em 390 px: as cinco rotas passaram na verificação de overflow e corte horizontal; capturas inspecionadas. É um ensaio, não o zoom nativo do navegador nem certificação WCAG.
- 32 verificações funcionais compartilhadas aprovadas em desktop e mobile: filtros, busca com acentos, vazio e recuperação, persistência e quantidades do carrinho, foco, menu, entrega/retirada, espaços em campos obrigatórios, rascunho seguro e invalidação da prévia.
- Mais 102 verificações de interação aprovadas no script compartilhado de Olivo/Maré, incluindo todas as etapas da história com movimento normal e reduzido e gestos de toque sintetizados. O Kintsuru usa rolagem horizontal nativa; não houve ensaio de gesto físico em iPhone.
- Detector Impeccable executado nas cinco URLs em 390×844 e 1440×900. Resultado final: apenas alertas de paleta creme (um por rota), que correspondem às referências aprovadas; não constituem defeitos desta entrega. Nenhuma configuração de exclusão foi adicionada para esconder resultados. Os alertas de texto pequeno e de contraste encontrados foram corrigidos; os alertas de última palavra isolada desapareceram após text-wrap:pretty.
- Cores corrigidas sem painéis ou backgrounds novos para texto. As fotografias e superfícies de marca foram preservadas.
- Capturas e medições: `../artifacts/mare-kintsuru-audit-before/`, `../artifacts/mare-kintsuru-audit-final/`, `../artifacts/mare-kintsuru-audit-after/` e `../artifacts/mare-kintsuru-functional/`. A infraestrutura visual antiga não está presente; foram usados os scripts CDP compartilhados em `../scripts/`. Artefatos de execução não foram adicionados ao Git.
- Não houve avaliação em Safari/Firefox, leitor de tela, aparelho físico ou Core Web Vitals em campo. Controles inativos de WhatsApp e reservas reais continuam identificados como demonstração; não são tarefas de integração desta auditoria.

## Ordem aplicada

`adapt` e `typeset` para leitura/refluxo, `harden` para recuperação de estados, `optimize` onde necessário e `polish` para conferência final. As recomendações desta auditoria já foram implementadas; os limites de plataformas acima descrevem cobertura ainda não medida, não correções de interface deixadas pela metade.
