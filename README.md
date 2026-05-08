# 🤖 Case Nola: Chatbot de Suporte Inteligente (IA + n8n)

Este projeto foi desenvolvido como parte do desafio técnico para a vaga de **Analista de CS Pleno** na **Noah Sistemas**. O objetivo é otimizar a operação de suporte da **Nola**, garantindo agilidade, escala e precisão no atendimento ao cliente.

---

## 📌 Contexto do Projeto
O crescimento acelerado de uma operação de suporte técnico traz o desafio de manter a qualidade sem aumentar proporcionalmente o esforço humano. Este projeto utiliza Inteligência Artificial para automatizar respostas de dúvidas frequentes (FAQ), permitindo que o time de Customer Success foque em tarefas de alto valor e relacionamento estratégico.

---

## 🛠️ Arquitetura da Solução
A automação foi construída utilizando uma abordagem *low-code* e escalável:

1.  **Interface de Entrada:** Webhook (integrado a uma interface HTML/Postman).
2.  **Base de Conhecimento:** Google Sheets (atuando como o cérebro da operação).
3.  **Orquestração:** n8n (processamento e lógica de dados).
4.  **Motor de IA:** Groq API utilizando o modelo **Llama 3-8b-8192** (alta velocidade e precisão).
5.  **Interface de Saída:** Resposta estruturada via JSON.

---

## 🧠 Engenharia de Prompt
O comportamento da IA foi refinado através do seguinte *System Prompt*:

> *"Você é um assistente de suporte da Nola, sistema de gestão para restaurantes. Responda APENAS com base na base de conhecimento fornecida. Se a pergunta não estiver coberta, diga: 'Não encontrei essa informação. Vou acionar nosso time para te ajudar em breve!' Seja direto, claro e amigável."*

---

## 🚀 Valor para o Suporte e CS
Esta implementação impacta diretamente os principais KPIs da área:

*   **Redução do Tempo de Resposta (First Response Time):** Respostas instantâneas 24/7.
*   **Escalabilidade:** Capacidade de atender centenas de clientes simultaneamente com custo marginal próximo de zero.
*   **Single Source of Truth:** A base de conhecimento no Google Sheets garante que o bot nunca alucine, utilizando apenas informações aprovadas pelo time técnico.
*   **Foco Estratégico:** Redução do volume de tickets transacionais (ex: "como trocar senha"), liberando o analista de CS para atuar na retenção e expansão.

---

## 💻 Como o Fluxo Funciona (Lógica)
1. O nó **Webhook** recebe a pergunta do usuário.
2. O nó **Google Sheets** lê todas as linhas da planilha de FAQ.
3. Um nó **Code (JavaScript)** consolida os dados da planilha em um bloco de texto estruturado (Contexto).
4. O nó **HTTP Request** envia o contexto + a pergunta do usuário para a Groq API.
5. A resposta é filtrada e enviada de volta ao usuário através do nó **Respond to Webhook**.

---

## 🧰 Ferramentas Utilizadas
*   **n8n:** Orquestração de workflows.
*   **Groq API (Llama 3):** Processamento de linguagem natural.
*   **Google Sheets:** Gerenciamento de banco de dados.
*   **Claude/Gemini:** Apoio no refinamento da lógica e prompts.

---

## 👤 Desenvolvido por
**Camilla Paula Soares Santos**
*   Analista de Systems Analysis and Development.
*   Foco em Customer Success, Automação e Soluções Tecnológicas.
*   [LinkedIn](https://www.linkedin.com/in/camilla-paula-281088185) | [GitHub](https://github.com/CammillaPS) 
