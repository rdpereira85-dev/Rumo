# Instruções para o Claude (Claude Code)

Projeto: **Rumo**, PWA pessoal de gestão de projetos gamificada do Rafael. Usado no iPhone 14 via "Adicionar à Tela de Início", hospedado no GitHub Pages (`rdpereira85-dev/Rumo`).

## Estrutura
- `index.html` — app inteiro (HTML + CSS + JS puro, sem build, sem dependências externas)
- `sw.js` — service worker para uso off-line (estratégia rede-primeiro com fallback de cache)
- `manifest.json` + `icon-*.png` — instalação como app

## Regras ao alterar
- Manter tudo em um único `index.html`, sem frameworks nem CDNs (precisa funcionar off-line).
- Textos da interface em português do Brasil.
- Cores sempre via variáveis CSS em `:root`; todo novo componente deve funcionar nos temas claro, escuro e automático.
- Layout mobile-first (≈390px), respeitando `env(safe-area-inset-*)`.
- **Nunca quebrar dados salvos:** chave `rumo-v1` no localStorage. Ao adicionar campos, trate a ausência deles (dados antigos). Se mudar o formato, escreva uma migração.
- A cada mudança: atualizar `VERSION` no `index.html` e `CACHE` no `sw.js`.

## Modelo de dados (localStorage `rumo-v1`)
```
{ projects:[{id,name,cat,goal,why,deadline,created,completed,
             tasks:[{id,title,weight(1-3),done,doneAt,subs:[{id,title,done}]}]}],
  xp, log:{'AAAA-MM-DD':nAvancos}, badges:[ids], theme:'auto'|'light'|'dark',
  focus:{date,ids:[taskIds]}, stats:{actions,tasksDone,projectsDone,imports}, version }
```

## Formato de importação de tarefas geradas pelo Claude
`{"tasks":[{"title":"...","weight":2,"subs":["...","..."]}]}`
