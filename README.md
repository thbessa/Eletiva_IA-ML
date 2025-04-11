# 🤖 Automação de Chatbot via Telegram - Vammo

Este repositório contém os fluxos de automação desenvolvidos em **n8n** para a empresa **Vammo**, especializada em aluguel de motos diretamente para entregadores. A automação está integrada com o **Telegram** e o **Google Sheets**, com o apoio de inteligência artificial da **OpenAI** para relatórios automáticos.

---

## 🧩 Visão Geral da Automação

A solução é composta por **dois fluxos principais**, organizados para otimizar a **qualificação de leads** e a **inteligência operacional**:

### 1. Agente de Qualificação de Leads

Fluxo responsável por interagir com leads automaticamente via Telegram, coletando e analisando dados para determinar se o potencial cliente está qualificado.

#### Funcionalidades:

- Início automático da conversa quando um lead entra no Telegram.
- Coleta das seguintes informações:
  - Interesse no aluguel de motos
  - Possui ou não CNH válida
  - Intenção de uso
- Encaminhamento automático de leads qualificados (com CNH e interesse) para o **time de vendas (closer)**.
- Registro completo da interação no **CRM (Google Sheets)**, incluindo:
  - Dados fornecidos
  - Histórico da conversa

#### Tecnologias utilizadas:
- [n8n](https://n8n.io/)
- [Telegram Bot API](https://core.telegram.org/bots/api)
- Google Sheets (via n8n)
- Webhooks

---

### 2. Agente de Relatórios Inteligentes

Automação responsável por analisar periodicamente os dados do CRM e gerar relatórios gerenciais com o apoio de IA.

#### Funcionalidades:

- Coleta e análise automática dos dados do Google Sheets e do histórico de mensagens.
- Utilização da **OpenAI** para gerar um relatório estratégico contendo:
  - Número de leads atendidos
  - Quantos tinham ou não CNH
  - Quantos foram encaminhados para o closer
  - Casos de insatisfação (com nome e ID do cliente)
  - Análise qualitativa sobre a fluidez das conversas
  - Sugestões de melhoria na comunicação e no processo de qualificação
- Geração de relatório em **HTML**
- Envio automático por e-mail para o time responsável

#### Tecnologias utilizadas:
- n8n
- Google Sheets
- OpenAI API
- E-mail SMTP
- HTML Report Formatter

---

## 📁 Estrutura do Repositório

📦 chatbot-n8n ├── chatbot-workflow.json # Fluxo de qualificação de leads ├── reports-agent.json # Fluxo de geração de relatórios com IA ├── README.md # Este arquivo └── /docs # (opcional) Imagens e documentação complementar


---

## 🚀 Como usar

1. Importe os arquivos `.json` no painel do n8n usando a opção **"Import workflow"**.
2. Configure as credenciais:
   - Telegram Bot Token
   - Conexão com Google Sheets (OAuth2 ou API Key)
   - Conta SMTP para envio de e-mails
   - Chave da API OpenAI
3. Ative os fluxos no modo **"Active"**.
4. (Opcional) Agende a automação do relatório via **Cron** no n8n.

---

## 🛠 Requisitos

- n8n (versão recomendada: `>=0.240.0`)
- Conta no Telegram com bot configurado
- Conta Google com acesso ao Google Sheets
- Chave de API da OpenAI
- Servidor ou ambiente para manter o n8n rodando (ex: Docker, VPS, etc.)

---

## 🧠 Considerações finais

Essa automação foi desenvolvida para garantir **eficiência na pré-venda**, **organização de dados** e **inteligência operacional** através de ferramentas de automação e IA.  
A estrutura modular permite fácil escalabilidade e personalização.

---

## 📫 Contato

Para dúvidas técnicas ou sugestões, entre em contato com o time de desenvolvimento.

---

