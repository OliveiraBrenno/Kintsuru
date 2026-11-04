---
name: Kintsuru
description: Cozinha japonesa com expressão manuscrita, papel creme e alegria coral.
colors:
  cream: "#f9f1e5"
  paper: "#fff9f0"
  navy: "#102e3f"
  coral: "#f5806b"
  coral-dark: "#aa3929"
  green: "#315e49"
  muted: "#536057"
  line: "#dcd5c6"
typography:
  display:
    fontFamily: "Brush, cursive"
    fontSize: "clamp(54px, 5.8vw, 84px)"
    fontWeight: 700
    lineHeight: 1.03
    letterSpacing: "-0.025em"
  headline:
    fontFamily: "Brush, cursive"
    fontSize: "40px"
    fontWeight: 700
    lineHeight: 1.03
  title:
    fontFamily: "DM, sans-serif"
    fontSize: "17px"
    fontWeight: 700
    lineHeight: 1.3
  body:
    fontFamily: "DM, sans-serif"
    fontSize: "15px"
    fontWeight: 400
    lineHeight: 1.55
  label:
    fontFamily: "DM, sans-serif"
    fontSize: "14px"
    fontWeight: 700
    lineHeight: 1.4
rounded:
  field: "7px"
  floating: "12px"
  product: "15px"
  surface: "16px"
  pill: "50px"
spacing:
  compact: "8px"
  control-gap: "10px"
  small: "15px"
  medium: "20px"
  grid: "24px"
  panel: "23px"
  section: "35px"
components:
  button-coral:
    backgroundColor: "{colors.coral}"
    textColor: "#142f39"
    rounded: "{rounded.pill}"
    typography: "{typography.label}"
    padding: "11px 23px"
    height: "46px"
  button-coral-hover:
    backgroundColor: "#fa9a82"
  button-green:
    backgroundColor: "{colors.green}"
    textColor: "{colors.paper}"
    rounded: "{rounded.pill}"
    padding: "11px 23px"
    height: "46px"
  button-green-hover:
    backgroundColor: "#214d38"
  button-cream:
    backgroundColor: "{colors.paper}"
    textColor: "{colors.navy}"
    rounded: "{rounded.pill}"
    padding: "11px 23px"
  button-outline:
    backgroundColor: "transparent"
    textColor: "{colors.green}"
    rounded: "{rounded.pill}"
    padding: "11px 23px"
  filter:
    backgroundColor: "transparent"
    textColor: "{colors.navy}"
    rounded: "30px"
    padding: "8px 14px"
  filter-selected:
    backgroundColor: "{colors.green}"
    textColor: "{colors.paper}"
  product-card:
    backgroundColor: "{colors.paper}"
    textColor: "{colors.navy}"
    rounded: "{rounded.product}"
  field:
    backgroundColor: "#fffcf7"
    textColor: "{colors.navy}"
    rounded: "{rounded.field}"
    padding: "10px"
    width: "100%"
  navigation-current:
    backgroundColor: "{colors.coral}"
    textColor: "{colors.navy}"
    rounded: "30px"
    padding: "8px 15px"
  order-panel:
    backgroundColor: "{colors.paper}"
    rounded: "{rounded.surface}"
    padding: "23px"
---

# Design System: Kintsuru

## Overview

**Creative North Star: "Tradição com um toque de alegria"**

O Kintsuru combina a leveza do papel creme, escrita de pincel e comida fotografada com presença. Marinho estrutura a leitura; coral dá calor aos convites; verde sustenta pedidos e encontros. A expressão é acolhedora, ilustrada e legível.

A autoridade visual é o mockup Kintsuru fornecido pelo usuário. A logo com tsuru, o mascote sushi, as ondas e as flores preservam essa identidade. Os arquivos raster de logo e mascote são reproduções geradas da referência, e a arte principal foi criada para esta implementação; não são os vetores originais. Esta documentação extrai o código existente e não propõe outra direção.

**Key Characteristics:**

- Títulos manuscritos contrastam com informações e controles em sans-serif.
- Papel claro, marinho profundo, coral caloroso e verde de algas formam a identidade.
- Fotografia de comida e ilustração japonesa convivem sem cobrir os controles.
- Superfícies arredondadas e sombras discretas mantêm o conteúdo acolhedor e organizado.

**The Reference Rule.** Preserve a logo, o mascote e a linguagem japonesa estabelecidos pelo mockup ao ampliar a interface.

## Colors

Os valores normativos estão no frontmatter e correspondem às propriedades do arquivo de estilos.

### Primary

- **Marinho profundo — navy:** texto principal, títulos, ícones e mensagens temporárias.
- **Coral salmão — coral:** chamadas principais, página atual na navegação e seleção de texto.
- **Coral de tinta — coral-dark:** ênfase manuscrita, foco de teclado e cursor dos campos; a variação mais escura sustenta a leitura sobre fundo claro.

### Secondary

- **Verde de algas — green:** conclusão do pedido, reservas, filtros selecionados, links e faixa com mascote.

### Neutral

- **Papel creme — cream:** fundo contínuo da página.
- **Papel claro — paper:** cartões, painel do pedido, botão claro e texto sobre verde.
- **Cinza vegetal — muted:** descrições, informações auxiliares e notas.
- **Divisória de papel — line:** separação do rodapé, subtotal e itens do pedido.

Fundos pêssego, etiqueta amarela do chef e variações de hover são tratamentos locais observados; não constituem novas cores de marca.

**The Readable Coral Rule.** Use o coral de tinta para ênfases textuais sobre papel e o coral salmão como superfície de ação.

## Typography

**Display Font:** Caveat, carregada localmente sob o nome CSS Brush, com fallback cursive.

**Body Font:** DM Sans, carregada localmente sob o nome CSS DM, com fallback sans-serif. Ambas usam font-display swap e arquivos WOFF2 locais.

**Character:** O pincel cria proximidade nos títulos; a sans-serif mantém produtos, preços, formulários e navegação precisos. O português usa caixa natural.

### Hierarchy

- **Display:** título principal fluido conforme o token; títulos das páginas internas usam tamanho próprio (64px), reduzido no celular (48px).
- **Headline:** títulos de seção partem do token; variações observadas vão de (33px) nos grupos do cardápio a (47px) na apresentação da casa.
- **Title:** nomes dos produtos usam a sans-serif; no cardápio reduzem para (16px) e, no celular, (14px).
- **Body:** texto base conforme o token; descrições de produtos usam (13px), informações de apoio ficam entre (10px) e (12px).
- **Label:** botões usam o token; filtros usam (12px, peso 600). Preços e subtotal usam algarismos tabulares.

**The Clear Order Rule.** Reserve a escrita de pincel para títulos e expressões da marca; mantenha preços, quantidades e formulários em DM Sans.

## Layout

O contêiner central tem largura máxima (1200px) e desconta (80px) da janela. Até (1100px), desconta (48px); até (760px), desconta (36px). A navegação ocupa altura mínima (108px), reduzida a (85px) no celular.

No desktop, o início combina texto à esquerda com arte sobreposta à direita, cinco categorias, três cartões do chef e duas faixas de convite. A apresentação da casa usa duas colunas. O cardápio combina uma região flexível com painel de pedido (350px), reduzido a (320px) até (1100px); os produtos usam duas colunas. Unidades usam três colunas. Espaços de grade recorrentes estão no frontmatter; respiros entre seções variam conforme a composição existente.

Até (760px), o hero empilha texto e arte; categorias viram uma faixa horizontal com encaixe de rolagem, e cartões do chef também rolam horizontalmente. Convites, apresentação e unidades passam a uma coluna. O painel do pedido segue abaixo dos produtos, sem posição fixa. O atalho inferior aparece quando há itens, mostra subtotal e leva o foco ao título do pedido. As categorias do cardápio rolam horizontalmente; a grade mantém duas colunas até (360px), quando passa a uma.

Em telas a partir de (1500px), a arte principal aumenta sua participação e o hero cresce. Esses limites são os usados no código, não uma escala de dispositivos adicional.

**The Reachable Order Rule.** Mantenha o painel ao lado do cardápio no desktop e o atalho inferior com subtotal quando houver itens no celular.

As fotografias de todos os itens e das três unidades são geradas para a marca. Aplicar creme, coral, verde e marinho em louças, guardanapos, embalagens e ambientes, com tsuru e ondas em detalhes. Cada prato tem fotografia correspondente; as unidades têm ambientes distintos.

## Elevation & Depth

A profundidade vem do contraste entre papel, superfícies tonais e fotografias recortadas. Sombras são ambientes discretos, presentes em cartões de produto, painel do pedido e elementos flutuantes. A arte principal se dissolve no fundo com máscara em gradiente; no celular, a máscara muda da direção horizontal para vertical.

### Shadow Vocabulary

- **Cartão de produto:** sombra quente e leve (0 5px 14px #7e503010).
- **Painel do pedido:** sombra difusa discreta (0 8px 25px #654d2d0d).
- **Navegação móvel:** elevação sobre o conteúdo (0 10px 24px #102e3f1c).
- **Mensagem temporária:** sombra marinha (0 8px 25px #102e3f25).
- **Atalho móvel:** sombra marinha mais presente (0 6px 24px #102e3f30).

O botão coral possui duas bordas internas suaves, dando acabamento à sua superfície sem adicionar outro cartão.

## Shapes

Cartões de produto têm curvas ligeiramente menores que as faixas, unidades e painel; os raios estão no frontmatter. Campos usam curvas compactas, enquanto botões, filtros, etiquetas e quantidades adotam cápsulas. Setas de cartões e indicadores de quantidade são circulares. Fotos respeitam o recorte dos cartões; logo e mascote preservam sua transparência e usam ajuste integral, sem cortar a silhueta.

## Components

### Buttons

Botões são cápsulas com ícone linear e texto firme. Coral marca os convites principais; verde marca pedidos e reservas; papel claro contrasta com a faixa verde; contorno verde atende ações secundárias. Altura mínima e preenchimento do botão padrão estão no frontmatter; variantes compactas de navegação e pedido ajustam a densidade ao contexto.

No hover, botões sobem discretamente (-2px) e suas variantes mudam de fundo em (0.2s). O foco visível de toda a interface usa contorno coral de tinta (3px), afastado (4px). Desabilitados têm opacidade (0.45) e cursor de indisponibilidade. Não existe um tratamento visual próprio para pressionamento contínuo.

### Chips

Filtros do cardápio são cápsulas com contorno vegetal (1px), texto compacto e fundo transparente. O selecionado usa verde com texto de papel e comunica a seleção por aria-pressed. Hover não selecionado recebe fundo vegetal claro. A etiqueta do chef é amarela, pequena e inclui ícone e texto.

### Cards / Containers

Produtos combinam foto, nome, porção, descrição e uma linha inferior de preço com ação. Descrições ocupam a área flexível para alinhar o rodapé. O cartão de destaque usa seta circular; o cardápio usa botão Adicionar. Produtos sem foto exibem uma superfície vegetal com ícone e a frase “Feito com carinho”. Unidades reutilizam papel e curvas, com foto, dados e botão verde em largura total.

### Inputs / Fields

Campos, áreas de texto e seletores têm fundo de papel quase branco, contorno vegetal (1px), curva compacta e rótulo persistente. O foco usa o mesmo contorno global. Áreas de texto podem crescer verticalmente. Rádios usam verde. O endereço fica visível e obrigatório para entrega e desaparece na retirada. Campos obrigatórios usam validação nativa do navegador; não há um estilo de erro customizado.

### Navigation

Logo à esquerda, links centrais e chamada coral à direita. A página atual usa cápsula coral e aria-current; hover usa papel pêssego. Até o limite móvel, os links recolhem em um painel de papel acionado pelo botão com rótulo e aria-expanded; Escape fecha o painel. O link de salto para o conteúdo aparece ao receber foco.

### Order Panel

O painel de papel fica aderente ao topo no desktop, com limite de altura da janela e rolagem interna. O vazio mostra ícone, título curto e orientação. Com itens, cada linha tem nome, total da linha e controle de quantidade; ao chegar a zero, a linha desaparece. O máximo é (99) unidades, quando o incremento fica desabilitado. O envio fica desabilitado enquanto o pedido estiver vazio. Contagem e valores acompanham os mesmos dados no painel e no atalho móvel. O cabeçalho contém apenas logo e navegação.

### Feedback & Motion

A mensagem temporária usa marinho e papel, aparece perto da borda inferior, sobe suavemente e some após (2600ms). No celular fica acima do atalho de pedido. A região de itens anuncia atualizações com aria-live polite. O texto principal entra uma vez com deslocamento, desfoque e transparência (0.85s, cubic-bezier(0.16, 1, 0.3, 1)). Imagens e categorias têm aproximação ou deslocamento breve no hover. A preferência por redução de movimento remove animações, transições e rolagem suave.

## Do's and Don'ts

### Do:

- **Do** preservar a logo com tsuru e o mascote sushi derivados da referência vinculante.
- **Do** usar os tokens existentes de papel, marinho, coral e verde para novas superfícies.
- **Do** manter preços, quantidades, dados e formulários em DM Sans.
- **Do** conservar foco visível, seleção por atributos acessíveis e redução de movimento.
- **Do** adaptar grades, navegação e acesso ao pedido conforme os limites registrados.

### Don't:

- **Don't** substituir a identidade do mockup por uma nova linguagem visual.
- **Don't** apresentar as reproduções raster como arquivos vetoriais originais da marca.
- **Don't** cortar a silhueta da logo ou do mascote para preencher uma área de imagem.
- **Don't** usar a escrita de pincel nos controles de quantidade ou no formulário do pedido.
