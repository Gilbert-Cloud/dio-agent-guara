# 🤖 DIO Agent

> Seu mentor com Inteligência Artificial para aprender mais e melhor na [DIO](https://dio.me).

O **DIO Agent** é um agente de IA que acompanha você na sua jornada de estudos. Ele conhece as experiências da DIO (Bootcamps, Formações, Cursos, Desafios e muito mais) e ajuda você a estudar, praticar e planejar a sua carreira.

Você não precisa saber programar nem instalar nada complicado. Em **3 passos**, o seu mentor está pronto para usar.

---

## Sobre esta versão: o Guará, um DIO Agent de segurança

Peguei o DIO Agent original e dei a ele uma especialidade nova: análise de vulnerabilidades. Como ele ganhou cara própria, resolvi batizar essa versão de **Guará** — o lobo-guará, aquele bicho do Cerrado que anda sozinho e vive de olho em tudo. Achei que casava com a função: um mentor que fica rondando o código à procura de brecha.

A ideia partiu do Desafio de Projeto da DIO, mas, sendo sincero, foi o trabalho que mais me deu gosto de fazer até agora. Não treinei modelo nenhum. O Guará aprendeu só pelo que está escrito nos arquivos do projeto, e é justamente isso que me fascina: dá pra especializar um agente inteiro escrevendo bem, sem uma linha de código de IA. Rodei tudo no **Google Antigravity**, abrindo a pasta do projeto direto nele.

### O que ele faz de diferente

O DIO Agent comum responde a pergunta e segue em frente. O Guará não faz isso. Quando você joga um código pra ele, a primeira coisa que ele faz é perguntar o contexto: isso roda onde? Está exposto na internet? Mexe com dado sensível? Só depois ele crava um veredito. Foi de propósito. Um analista de segurança de verdade não sai dando diagnóstico sem olhar o cenário, porque a mesma falha pode ser um susto pequeno ou um desastre, dependendo de onde ela está.

Ele também não entrega a correção mastigada. Aponta o problema, explica o conceito e deixa você escrever a solução. Depois revisa. É a mesma filosofia do DIO Agent original ("formar autonomia, não dar resposta pronta"), só que agora virada para a segurança.

### Os arquivos que criei e alterei

Pra ensinar essa habilidade ao agente, mexi nestes pontos do projeto:

**Criei:**
- `skills/vulnerability-analysis/SKILL.md` — o roteiro que o Guará segue na análise, com as regras defensivas e o formato padrão do laudo.
- `skills/vulnerability-analysis/README.md` — a explicação da skill para quem for ler.
- `agent/knowledge/security-basics.md` — a base de conceitos: vulnerabilidade, ameaça, risco, a tríade CIA e as referências CWE, OWASP e MITRE ATT&CK.
- `laboratorio/app_vulneravel.py` — um login em Python com SQL Injection, de propósito, pra servir de alvo.
- `laboratorio/app_corrigido.py` — o mesmo login, agora seguro, com consulta parametrizada.
- `laboratorio/README.md` — como rodar o laboratório e conversar com o agente.

**Alterei:**
- `agent/persona.md` — acrescentei o trecho que dá nome e postura ao Guará quando ele veste o chapéu de segurança.
- `AGENTS.md` — registrei a skill na tabela e a base de conhecimento, pro agente saber quando usar.
- `README.md` — esta seção e a skill na tabela lá embaixo.

### A melhoria que escolhi

Entre as ideias que a Expert deixou no fim das aulas, fiquei com a de **padronizar o laudo**. Toda análise do Guará sai no mesmo formato: vulnerabilidade, técnica do MITRE, parte da tríade CIA afetada, impacto, probabilidade, severidade, correção e status. Isso está dentro do `SKILL.md`, no Passo 3. Escolhi essa porque é o que separa um palpite solto de um relatório que presta: com todo caso saindo igual, dá pra comparar um com o outro, do jeito que um time de segurança faz de verdade. De quebra, a skill ficou genérica o suficiente pra rodar em outros cenários, como configuração insegura ou senha largada no código, não só no SQL Injection.

### Como rodar

1. Baixe este repositório com `git clone` ou pelo botão **Code → Download ZIP** no GitHub.
2. Abra a **pasta do projeto** no **Google Antigravity** (ou em outro harness que leia o `AGENTS.md`). Esse detalhe importa: se você abrir o harness fora da pasta, ele não acha os arquivos da skill e do conhecimento, e o Guará vira um agente comum.
3. Peça a análise. Eu uso algo assim:
   > *"Guará, analisa o `laboratorio/app_vulneravel.py` como especialista em segurança. É código meu, de laboratório."*
4. Repare nele perguntando o contexto antes de responder, classificando a falha (CWE-89 / OWASP A03 / MITRE T1190) e devolvendo o laudo padronizado. Depois mostre o `laboratorio/app_corrigido.py` e peça uma nova varredura, pra confirmar que o SQL Injection foi fechado.

Uma comparação que rende um bom print: faça a mesma pergunta num chat genérico, sem esses arquivos. Ele costuma responder na lata, sem pedir contexto e sem padronizar nada. A diferença toda está nos arquivos, não no modelo.

---

## ✨ Três palavras para começar

- 🧠 **Agente de IA:** um chatbot responde perguntas. Um *agente* vai além: lê, planeja e executa passos para ajudar você a alcançar um objetivo. É a diferença entre alguém que explica o caminho e alguém que caminha junto com você.
- 🖥️ **Harness:** é o programa onde o agente roda. O agente é o mentor, e o harness é a sala onde vocês se encontram. O mesmo mentor atende em salas diferentes, por isso o DIO Agent funciona em vários harnesses.
- 🧩 **Skill:** é uma habilidade do agente, descrita em um guia passo a passo. Você não precisa chamar a skill: o agente percebe o que você precisa e usa a certa sozinho.

Esses e outros termos estão no [Glossário](docs/glossary.md).

---

## 🚀 Comece em 3 passos

### 1️⃣ Instale um harness

Recomendamos o **Google Antigravity**, que tem limites de uso generosos para quem está começando. Mas qualquer harness da lista funciona: escolha um e siga a instalação da documentação oficial dele.

| Harness | Documentação oficial |
|---------|----------------------|
| Google Antigravity (recomendado) | https://antigravity.google/docs |
| Claude Code | https://code.claude.com/docs |
| Codex | https://developers.openai.com/codex |
| OpenCode | https://opencode.ai/docs |
| Hermes | https://hermes-agent.nousresearch.com/docs |

### 2️⃣ Baixe o DIO Agent e abra no harness

Baixe este repositório do jeito mais simples para você:

- **Com Git:** no terminal, rode `git clone https://github.com/digitalinnovationone/dio-agent.git`
- **Sem Git:** no topo desta página, clique no botão verde **Code**, depois em **Download ZIP**, e extraia a pasta.

Depois, abra no harness a pasta do projeto, a que tem o arquivo `AGENTS.md` (pelo Git, ela se chama `dio-agent`; pelo .zip, `dio-agent-main`). O harness lê esse arquivo sozinho, e o agente já sabe quem é: o seu mentor de estudos da DIO.

### 3️⃣ Converse

Fale naturalmente, com as suas palavras. Nas primeiras vezes, vale usar um dos [modelos de prompt](#-modelos-de-prompt) abaixo: quanto mais contexto você dá, melhor o agente ajuda.

---

## 🧩 As skills do agente

| Skill | Para que serve | Experimente pedir |
|-------|----------------|-------------------|
| [Plano de estudos](skills/study-plan/SKILL.md) | Organiza o que estudar, em que ordem e em quanto tempo | "Quero concluir este Bootcamp em 2 meses, me ajuda?" |
| [Destravar desafio](skills/unblock-challenge/SKILL.md) | Conduz você até a solução de um desafio, sem dar a resposta pronta | "Travei nesse desafio, me ajuda?" |
| [Explicar conceito](skills/explain-concept/SKILL.md) | Explica conceitos de forma simples, com analogias e exemplos | "Não entendi o que é uma API." |
| [Pesquisa na web](skills/web-search/SKILL.md) | Responde dúvidas atuais (versões, lançamentos, mercado) com fontes citadas | "Qual a versão estável do Node hoje?" |
| [Revisão de portfólio](skills/portfolio-review/SKILL.md) | Dá feedback sobre o seu portfólio e GitHub antes de buscar vagas | "O que falta no meu GitHub para uma vaga júnior?" |
| [Caminho AI Builder](skills/ai-builder-path/SKILL.md) | Ajuda você a escolher o próximo passo na Carreira AI Builder | "Qual Formação AI Builder combina comigo?" |
| [Análise de vulnerabilidades](skills/vulnerability-analysis/SKILL.md) | Analisa segurança de um código seu de laboratório (AppSec), explica a falha e orienta a correção, sem dar a resposta pronta | "Analisa esse login em Python? Acho que tem SQL Injection." |

A pesquisa na web usa a busca do seu harness. Se ele não tiver busca própria, veja [como conectar o You.com](docs/youcom-mcp.md), que tem uma opção gratuita.

---

## 📝 Modelos de prompt

Copie, preencha o que está entre colchetes e envie. Não precisa de formato perfeito: o agente pede mais detalhes se precisar.

**🗺️ Plano de estudos**

```
Quero montar um plano de estudos.
- Meu objetivo: [ex: ser dev back-end, concluir um Bootcamp]
- O que quero fazer na DIO: [link ou nome do Bootcamp, Formação, Aceleração ou Carreira]
- O que já tenho: [um plano de ação ou de estudos, se tiver]
- Meu nível hoje: [iniciante, intermediário, avançado]
- Tempo disponível: [ex: 1 hora por dia, de segunda a sexta]
```

**🔓 Destravar desafio**

```
Estou travado em um Desafio de [Código, Projeto ou Criativo] da DIO.
- O que o desafio pede: [cole o enunciado ou, no Desafio de Projeto, o link do repositório do desafio]
- Onde eu travei: [explique o ponto da dificuldade]
- Meu código ou repositório: [cole o código ou o link, se tiver]
Me ajuda a destravar sem dar a resposta pronta.
```

**💡 Explicar conceito**

```
Me explica o conceito de [ex: API, laço de repetição, herança].
- Meu nível: [nunca vi, já ouvi falar, quero aprofundar]
```

**🧭 Caminho AI Builder**

```
Quero escolher meu próximo passo na Carreira AI Builder.
- O que quero construir com IA: [ex: um produto para o meu negócio, um software, agentes que automatizam processos, ainda não sei]
- Minha experiência com programação: [nenhuma, o básico, trabalho com desenvolvimento]
- Meu objetivo: [ex: mudar de carreira, tirar uma ideia do papel]
```

---

## 🔄 Mantenha o DIO Agent atualizado

O DIO Agent evolui com o tempo. Se você usou Git, rode `git pull` no terminal, dentro da pasta (ou peça para o próprio agente rodar). Se baixou o .zip, baixe de novo.

---

## 🗂️ Estrutura do repositório

```
dio-agent/
├── README.md                Este guia
├── AGENTS.md                Definição do agente (lida pelo harness)
├── CLAUDE.md                Atalho para o Claude Code
├── agent/
│   ├── persona.md           A personalidade e o tom do agente
│   └── knowledge/           O que o agente sabe sobre a DIO
├── skills/                  Uma pasta por skill, cada uma com o seu SKILL.md
└── docs/
    ├── glossary.md          Glossário de termos
    └── youcom-mcp.md        Como conectar a busca do You.com
```

---

## 🤝 Contribua

Tem uma ideia de skill? Veja [como criar uma skill](skills/README.md) e abra um pull request.

---

## 💬 Sobre este projeto

O DIO Agent foi criado para acompanhar você nos Bootcamps e Formações da DIO. A ideia é simples: aprender na era da IA fica mais fácil quando você tem um mentor disponível a qualquer hora.

Bons estudos, e vem com a gente. 🚀
