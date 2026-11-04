# Kintsuru

Site estático responsivo de um restaurante japonês fictício. Inclui início, cardápio com pedido persistido no navegador e unidades com reservas via WhatsApp.

## Executar

Requer Node.js. Sem instalação de dependências para executar o site:

```sh
npm run dev
```

Abra http://127.0.0.1:5180.

## Personalizar

- `config.js`: números WhatsApp das unidades, com país e DDD (somente dígitos). Sem número configurado, abre a mensagem no WhatsApp para escolher um destinatário. Nenhum pedido ou reserva é enviado automaticamente.
- `order.js`: pratos, preços em centavos, endereços e horários fictícios.
- `style.css`: identidade e comportamento responsivo.
- `assets/`: fotos, fontes, logo, arte principal e mascote.

`npm test` verifica totais e mensagens. `tests/capture.mjs` registra verificação de navegador e capturas; usa Playwright da instalação local vizinha do portfólio, somente como ferramenta de desenvolvimento.

Os formulários são locais. O carrinho é preservado em localStorage; os dados do formulário ficam apenas na sessão do navegador. Entrega, disponibilidade e confirmação final são combinadas com a unidade pelo WhatsApp.

## Identidade e imagens

Referência fornecida: `/Users/Brenno/Desktop/mockup kintsuru .png`. A logo e o mascote são reproduções preparadas com geração de imagem a partir da referência; não são arquivos vetoriais originais. A arte principal recria o universo de sushi, tsuru, flores e ondas. Fotografias dos 15 itens e das três unidades geradas para o Kintsuru, com louças, peças de mesa, sinalização e ambientes que aplicam a identidade da marca. Origens e prompts em `assets/SOURCES.md` e `assets/generated-manifest.json`.
