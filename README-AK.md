# Edna Vieira Joias — LP Pré-Black (Grupo VIP)

**Cliente:** Edna Vieira Joias — semijoias, 12 anos de marca, posicionamento em elegância
**Cidade:** Belo Horizonte/MG (e-commerce para todo o Brasil)
**Objetivo:** levar a visitante a entrar no Grupo VIP de WhatsApp do Esquenta Black / Pré-Black / Black Friday 2026

Landing page única, para link na bio do Instagram e tráfego pago no Meta.
Design "opção 3 · glass" aprovado no Claude Design.

## Stack

HTML, CSS e JS puros, tudo inline no `index.html`. Fontes do Google Fonts (Archivo + Instrument Serif).
Não usa o runtime do Claude Design (`support.js`) nem React, então não há `vendor/`.
**Sem framework, sem bundler, sem etapa de build.**

```
index.html      página completa (CSS e JS inline)
vercel.json     clean URLs + cache de assets
assets/         avatar, texturas de cetim, gema e pérola, favicons e og-image.jpg
```

## Deploy — Vercel

1. Importar este repositório no Vercel.
2. Framework Preset: **Other**.
3. Root Directory: **raiz do repositório**.
4. Sem Build Command, sem Install Command, sem Output Directory.

## Onde editar

Constantes no topo do `<script>` do `index.html`:

- `ESQUENTA` — data/hora do Esquenta Black (contagem regressiva). Hoje: 29/10/2026 00h.
- `PRE_BLACK` — data do Pré-Black. Vazio mostra "Em breve" na linha do tempo.
- `BLACK` — Black Friday (27/11/2026).
- Teste de headline: `?h=b` ou `?h=c` no link do anúncio (padrão `a`). O evento `Lead` leva a variante em `content_category`.

Link do grupo: no `href` dos dois botões `a[data-vip]`.

## Rastreio

- Meta Pixel `933272459243844` no `<head>` (PageView), copiado da página de link na bio que está no ar.
- `<noscript>` do pixel logo após a abertura do `<body>`.
- `fbq('track','Lead')` no clique de qualquer botão do grupo, uma vez por visita (cliques repetidos não duplicam). No celular o redirecionamento espera 300 ms para o evento sair.
- Domínio de produção: `https://grupo.ednavieira.com.br/` (destino das campanhas).

## Edições sobre o exportado

- Pixel do Meta inserido no lugar do comentário `[PIXEL]`.
- `<head>` estático: canonical, Open Graph (`og:*`, imagem 1200×630 em `assets/og-image.jpg`), `twitter:card` e favicons.
- Botões do grupo com o link real no `href` (antes era `#vip` trocado via JS) e marcados com `data-vip`;
  o script passou a só anexar o evento `Lead`.
- `assets/og-image.jpg` gerado do hero em 1200×630, com "Esquenta Black · 29/10" no lugar da contagem (que ficaria congelada na prévia).
- Favicons (`favicon-32.png`, `favicon-180.png`) gerados a partir do avatar (150 px de origem — trocar por logo em alta quando houver).

## Joias (20/10/2026)

Ajuste do Claude Design aplicado: diamante lapidado no hero, fio de pérolas nas duas emendas preto/claro,
pedrinhas turquesa no selo e na etapa ativa, brilhos no painel do fechamento. Assets novos: `assets/gema.png` e `assets/perola.png`.
Copy, layout, links, JS e pixel não mudaram.

## Pendências

- **Data do Pré-Black** (`PRE_BLACK`) a confirmar com a cliente.
- **Desconto direto** e **número real de prova** (clientes/avaliações) — marcados com `[CONFIRMAR]` no HTML.
- Confirmar que `chat.whatsapp.com/BYq6WAK46XSDqEeKW0pLBb` é o grupo certo para a Black.

Última atualização: 22/10/2026
