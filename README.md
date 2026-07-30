# Gerador de stacks — Salvy

Página estática, sem build. Abra `index.html` no navegador ou publique a pasta inteira.

## Publicar no GitHub Pages
1. Crie um repo (ex: `salvy-gerador-de-stack`).
2. Suba o conteúdo desta pasta na raiz do repo (`index.html` na raiz, não dentro de `dist/`).
3. Settings → Pages → Source: `Deploy from a branch` → branch `main`, pasta `/ (root)` → Save.
4. Em ~1 min a página fica em `https://<org>.github.io/<repo>/`.

Pelo terminal:

```bash
git init
git add .
git commit -m "gerador de stacks"
git branch -M main
git remote add origin git@github.com:SalvyLTD/salvy-gerador-de-stack.git
git push -u origin main
```

## Arquivos
- `index.html` — a página (editor + preview em canvas + export PNG)
- `support.js` — runtime que renderiza a página
- `assets/logo-salvy.svg` — logo Salvy (cabeçalho, rodapé da página, rodapé do PNG)
- `assets/icon-hand.svg` — mãozinha pixel do título
- `assets/logos/*` — logos monocromáticos embutidos

## Como os logos são resolvidos (em ordem)
1. `BUNDLED` — arquivos locais de `assets/logos` (Salvy y, Caju, Kamino, Conta Simples, Pipefy, Asaas, CloudHumans, Onfly, Chatwoot, Aircall, Mintlify, CodeRabbit).
2. Simple Icons via CDN jsDelivr — marca oficial monocromática (~90 ferramentas em `CATALOG`).
3. Favicon do site (mapa `DOMAINS`), convertido para preto no browser. Se sair fino demais, é descartado.
4. Sem logo: chip de texto. O botão `logo` no editor permite subir o oficial — convertido para preto e salvo em localStorage.

Para embutir um logo novo: salve o arquivo em `assets/logos/`, adicione em `BUNDLED` e, se for wordmark completo (dispensa o nome ao lado), em `WORDMARKS`.

## Export
Livre (1080px de largura, altura dinâmica), 1:1, 4:5 e Story — todos em 2x. O botão `Copiar legenda` gera o texto do post com as camadas e os perfis de LinkedIn das empresas citadas.