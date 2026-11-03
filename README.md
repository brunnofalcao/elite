# PALESTRE•SE ELITE 2027 · site de vendas

Site estático, uma página, mobile-first. Sem build: é só subir no GitHub e conectar ao Vercel (framework: Other, output: raiz).

## Estrutura
- `index.html` · a página inteira (CSS e JS embutidos, fontes e imagens em `/assets`)
- `obrigado.html` · página de retorno depois do checkout (configurar na Hotmart como URL de obrigado: `https://elite.palestre.se/obrigado`)
- `assets/fonts/` · Fraunces, Caveat e Inter, subconjunto latino em woff2 (OFL)
- `assets/img/` · lockups (webp + png), `og.jpg` (1200 × 630), `favicon.svg`
- `assets/elite-2027.ics` · convite de calendário
- `vercel.json` · URLs limpas e cache de 1 ano em `/assets`

## O que editar antes de publicar (topo do `<script>` no index.html)
- `LINKS` · os 4 checkouts da Hotmart (vip, ouro, prata, online). Vazio = o botão manda para o WhatsApp.
- `WHATSAPP` · número da equipe.
- `REVISAO` · `false` antes de publicar (esconde as etiquetas "confirmar" e os "@" vazios).
- `PALESTRAS_ELITE` · número de palestras do ELITE dos últimos 2 anos. Vazio = o número não aparece.
- `PHOTOS` · URLs das fotos em preto e branco: `time`, `brunno`, `thaisa`, `thiago`, `lucas`, `stevan`, galerias `e0…`, `r0…`, `m0…`, `s0…`. Coloque as fotos em `assets/img/` e use caminhos relativos.
- Nomes e @ das galerias: nos blocos `gal` do HTML (procure por "Quem já subiu no palco").
- Domínio: troque `https://elite.palestre.se` nas metatags `og:url` e `og:image` e no `obrigado.html`.

## Performance
Primeira pintura sem bloqueio: CSS crítico embutido, duas fontes pré-carregadas (Fraunces 600 e Inter 400), demais com `font-display: swap`; imagens com largura e altura reservadas; nenhum script externo; nada de Google Fonts em produção.
