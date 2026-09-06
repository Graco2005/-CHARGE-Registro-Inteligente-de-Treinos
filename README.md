# ⚡ Charge

> Registre. Compare. Evolua.

Charge é um aplicativo de acompanhamento de treinos de musculação desenvolvido como um único arquivo HTML — sem dependências externas, sem instalação, sem conta. Todos os dados ficam salvos localmente no navegador via `localStorage`.

---

## ✨ Funcionalidades

### Planejamento de Treino
- Criação de divisões personalizadas: **AB, ABC, ABCD ou ABCDE**
- Nome livre para cada divisão (ex: A = Pernas, B = Upper, C = Push)
- Montagem do treino base com exercícios, número de séries e repetições alvo por série
- Suporte a técnicas avançadas por exercício e por série: **Myo-Reps, Rest-Pause, Cluster, Drop-Set, RIR (0–3), AMRAP, Super-Série, Bi-Set**
- Múltiplos planos de treino com ativação de um como padrão
- Edição e exclusão de planos a qualquer momento

### Registro de Treino
- Tela de sessão com progresso visual em tempo real
- Preenchimento de **carga (kg), repetições e observações** para cada série
- Comparação automática com o último treino igual (cargas e reps anteriores como referência)
- Adição e remoção de séries extras durante o treino
- Campo de observações por exercício e observação geral do treino
- Registro de **Cardio** (tipo + duração) e **Abdominal** como extras do dia
- Sugestão automática do próximo treino na sequência da divisão

### Salvamento e Continuidade
- **Autosave automático** a cada 30 segundos durante o treino
- **Pausar e continuar depois**: salva o progresso e retoma quando quiser, com banner de aviso na tela inicial
- **Edição do treino do dia**: enquanto for o mesmo dia, é possível corrigir cargas e repetições já registradas
- **Registro retroativo**: clique em qualquer dia anterior na tela inicial para registrar um treino esquecido ou marcá-lo como descanso

### Dias de Descanso
- Registro de dias de descanso com observação opcional
- Remoção do registro de descanso caso mude de ideia

### Tela Inicial e Visualizações
- Barra semanal de 7 segmentos: **amarelo = treino ⚡**, **azul = descanso 🛌**
- Dias passados clicáveis para registro retroativo
- Fila de dias da semana com identificação visual do status de cada dia
- Saudação dinâmica por horário do dia

### Histórico
- Visualização de todos os treinos e descansos agrupados por mês
- Detalhamento completo de cada sessão: exercícios, séries, cargas, reps, extras e observações
- Edição de treinos do dia atual diretamente pelo histórico

### Estatísticas
- Total de treinos realizados
- Sequência de dias consecutivos (streak)
- Total de dias de descanso
- Volume total levantado em toneladas
- Heatmap de frequência das últimas 14 semanas

### Interface
- Design escuro por padrão com alternância para **modo claro**
- Preferência de tema salva automaticamente
- Menu lateral (hambúrguer) com navegação entre telas
- Logo clicável retorna para a tela inicial
- Toasts de feedback para todas as ações
- Totalmente responsivo e otimizado para mobile

---

## 🚀 Como usar

Não há instalação. Basta abrir o arquivo no navegador:

```bash
# Clone o repositório
git clone https://github.com/seu-usuario/charge.git

# Abra o arquivo no navegador
open charge.html          # macOS
xdg-open charge.html      # Linux
start charge.html         # Windows
```

Ou simplesmente faça o download do `charge.html` e abra direto — funciona offline.

### Publicar online (opcional)

Por ser um único arquivo estático, pode ser hospedado em qualquer lugar:

```bash
# GitHub Pages — basta subir o arquivo e ativar Pages na branch main
# Netlify Drop   — arraste o arquivo em netlify.com/drop
# Vercel         — vercel deploy --prod
```

---

## 🗂 Estrutura do projeto

```
charge/
├── charge.html     # Aplicação completa (HTML + CSS + JS em um único arquivo)
├── .gitignore
└── README.md
```

Toda a lógica está contida em `charge.html`:

| Seção | Responsabilidade |
|---|---|
| `:root` CSS vars | Tokens de design (dark + light mode) |
| Componentes CSS | Layout, cards, modais, sessão, histórico |
| Data Layer | `localStorage` via objeto `DB` |
| Wizard | Criação e edição de planos de treino |
| Session Engine | Autosave, pausar/retomar, edição, log retroativo |
| Render Functions | Home, Planos, Histórico, Stats, Sessão |

---

## 💾 Armazenamento de dados

Todos os dados são salvos no `localStorage` do navegador sob as chaves:

| Chave | Conteúdo |
|---|---|
| `charge_plans` | Array de planos de treino com splits e exercícios |
| `charge_sessions` | Array de sessões (treinos e descansos) |
| `charge_draft_session` | Rascunho de treino em andamento (autosave) |
| `charge_theme` | Preferência de tema (`dark` ou `light`) |

> **Atenção:** limpar os dados do site no navegador apaga todo o histórico. Para backup, use a função de exportação futura ou copie o `localStorage` manualmente via DevTools.

---

## 🛠 Tecnologias

- **HTML5** — estrutura e semântica
- **CSS3** — variáveis custom, grid, flexbox, animações, dark/light mode
- **JavaScript ES6+** — vanilla, sem frameworks ou dependências
- **Google Fonts** — Space Grotesk + Inter (carregadas via CDN)
- **localStorage** — persistência de dados no cliente

---

## 🗺 Roadmap

- [ ] Exportar/importar dados (JSON backup)
- [ ] Gráficos de evolução de carga por exercício
- [ ] PWA com ícone e modo offline completo
- [ ] Notificações de lembrete de treino
- [ ] Compartilhamento de planos de treino

---

## 📄 Licença

MIT — use, modifique e distribua à vontade.