# Rumo — Projetos em foco

App pessoal (PWA) para registrar projetos, quebrar em tarefas e subtarefas, acompanhar o % de conclusão e manter o foco com gamificação (XP, níveis, sequência de dias e conquistas). Funciona on-line e off-line, com tema claro, escuro ou automático.

## ✅ Checklist de instalação (GitHub Pages + iPhone)

- [ ] Entrar no GitHub (conta `rdpereira85-dev`)
- [ ] Criar um repositório novo chamado **Rumo** (público)
- [ ] Clicar em **Add file → Upload files** e enviar todos os arquivos desta pasta (`index.html`, `manifest.json`, `sw.js`, os 3 ícones `icon-*.png`, `README.md` e `CLAUDE.md`)
- [ ] Em **Settings → Pages**, escolher *Deploy from a branch* → `main` → `/ (root)` → Save
- [ ] Aguardar 1–2 minutos e abrir `https://rdpereira85-dev.github.io/Rumo/` no **Safari** do iPhone
- [ ] Tocar em **Compartilhar → Adicionar à Tela de Início**
- [ ] Abrir pelo ícone uma vez com internet (isso salva o app para uso off-line)
- [ ] Criar o primeiro projeto 🚀

## 🧠 Integração com o Claude

**Dentro do app (planejamento):** em cada projeto, toque em *Planejar com o Claude* → *Copiar pedido* → cole no app do Claude → copie a resposta (JSON) → cole de volta e toque em *Importar tarefas*. Em *Ajustes* há também um relatório geral para pedir ajuda na priorização da semana.

**Para evoluir o próprio app:**
- **Claude Code / Claude com acesso ao GitHub:** peça "abra o repositório rdpereira85-dev/Rumo e adicione X". O Claude edita os arquivos e faz o commit; o GitHub Pages publica sozinho.
- **Sem Claude Code:** mande o `index.html` atual no chat, peça a mudança e suba o arquivo novo no GitHub (substituindo o antigo).
- Depois de qualquer mudança, aumente a versão `CACHE` em `sw.js` para o iPhone pegar a atualização.

## 💾 Dados

Os dados ficam salvos **no próprio aparelho** (localStorage). Use *Ajustes → Exportar backup* de vez em quando — o arquivo também serve para levar tudo para outro aparelho.

## Como a pontuação funciona

| Ação | XP |
|---|---|
| Subtarefa concluída | +5 |
| Tarefa concluída | +10 × esforço (1 a 3) |
| Projeto criado | +10 |
| Tarefas importadas do Claude | +15 |
| Projeto 100% | +100 |

O % do projeto é ponderado pelo esforço: uma tarefa ●●● pesa 3× mais que uma ● e avança proporcionalmente às subtarefas concluídas.
