# Rafael Luzart Tattoo

Site do tatuador Rafael Luzart: hiper-realismo de alto padrão. A página tem o banner, os projetos recentes em carrossel, o portfólio, o "Quem sou", as avaliações do Google, o valor médio de uma tatuagem e o botão de orçamento pelo WhatsApp.

É um site estático: um `index.html` e a pasta `assets/` com as fotos. Não precisa de build nem de instalação. As fontes vêm do Google Fonts.

## Testar no computador

Abra o `index.html` no navegador (dois cliques no arquivo).

## Publicar

Funciona em qualquer hospedagem de site estático. Envie o `index.html`, o `favicon.png`, o `apple-touch-icon.png` e a pasta `assets/` juntos, mantendo a estrutura.

- **GitHub Pages:** neste repositório, vá em Settings → Pages → *Deploy from a branch* → `main` / `(root)`.
- **Vercel ou Netlify:** importe este repositório; não há comando de build.
- **Hostinger, Locaweb e similares:** envie os arquivos para a pasta `public_html`.

## Idiomas

O site abre sempre em português. Os botões no canto superior direito (PT, EN, ES) traduzem a página inteira, inclusive a mensagem do WhatsApp. Um link terminado em `?lang=en` ou `?lang=es` já abre em inglês ou espanhol.

Os textos em inglês e espanhol ficam no objeto `I18N`, no fim do `index.html`. Ao mudar um texto em português, mude também nas duas traduções.

## Onde editar

No fim do `index.html`, dentro do `<script>`, o objeto `site` guarda o conteúdo que muda com frequência:

- `estilos`: os cards do carrossel "Projetos recentes" (título, texto, foto e descrição da foto).
- `portfolio`: as fotos do portfólio, na ordem em que aparecem. Para acrescentar, coloque a foto em `assets/` e adicione `{ src: "assets/nome.webp", alt: "descrição" }`.
- `avaliacoes`: avaliações do Google (nome, tempo, texto). As que têm `foto` aparecem primeiro e abrem ampliadas ao toque.
- `whatsappBase` e `mensagemWhatsApp`: número e mensagem inicial do botão de orçamento.

Ficam direto no HTML: textos do banner, do "Quem sou" e do valor médio, a nota do Google (5,0 e 248 avaliações) e o link do Instagram.

## Fotos

- `assets/banner-2.webp`: foto do banner
- `assets/quem-sou-2.webp`: foto do "Quem sou"
- `assets/estilo-rafael-*.webp`: fotos do carrossel "Projetos recentes"
- `assets/portfolio-r*.webp`: fotos do portfólio
- `assets/avaliacao-*.webp`: fotos enviadas pelos clientes nas avaliações

As fotos do carrossel e do portfólio têm uma versão menor com `-480` no nome, e o banner e o "Quem sou" têm `banner-2-800.webp` e `quem-sou-2-720.webp`. O celular carrega a versão menor e o computador a maior. Ao trocar uma foto, troque as duas versões.

## Desempenho

`_headers` (Netlify e Cloudflare Pages) e `vercel.json` (Vercel) mandam o navegador guardar as fotos em cache por 1 ano. Por isso, ao trocar uma foto, use um nome de arquivo novo em vez de substituir o arquivo com o mesmo nome. No GitHub Pages esses arquivos não têm efeito.
