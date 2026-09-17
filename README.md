# Chatbot Especialista — Mentor API

## Descrição do projeto

Este projeto implementa um **chatbot especialista educacional**, o
**Mentor API**, criado para ajudar estudantes e pessoas iniciantes no
mercado de trabalho a entenderem o que são APIs. O bot foi construído
usando engenharia de prompt (papéis *system*, *user* e *assistant*),
utilizando o **Google Gemini** como provedor de LLM.

O bot foi projetado para:
- Responder perguntas **exclusivamente** sobre o tema APIs (definição,
  API Gateway, proxy, REST, SOAP, GraphQL, arquiteturas SOA/microsserviços,
  webhooks, chamadas REST e boas práticas), evitando "alucinar" respostas
  sobre assuntos fora desse contexto.
- Aceitar **até 3 perguntas** por sessão de estudo.
- Ao final da 3ª resposta, gerar automaticamente um **resumo** de tudo
  que foi respondido na conversa e **encerrar a sessão**.

O prompt de sistema é composto por três elementos, seguindo o exemplo do
curso *ChatGPT Prompt Engineering for Developers* (DeepLearning.AI):
1. **Personalidade** do assistente virtual ("Mentor API"), com tom
   didático e paciente.
2. **Objetivo e tarefa** (regras de quantidade de perguntas, resumo e
   encerramento, e restrição de escopo ao tema APIs).
3. **Conhecimento** necessário (material de estudo sobre APIs).

## Pré-requisitos

- Uma conta Google (para rodar no Google Colab)
- Uma chave de API do Google AI Studio (gratuita):
  https://aistudio.google.com/app/apikey

## Passo a passo para reproduzir a execução

1. Acesse https://colab.research.google.com/ e faça login com sua conta Google.
2. Clique em **Arquivo > Fazer upload de notebook** e selecione o
   arquivo `mentor_api_chatbot.ipynb` deste repositório.
3. Crie sua chave de API seguindo os passos em
   https://aistudio.google.com/app/apikey
4. Configure a chave de uma das duas formas:
   - **Via `.env`:** copie
     o arquivo `.env.example` para `.env`, preencha com sua chave
     (`GOOGLE_API_KEY=sua-chave-aqui`), e faça upload do `.env` para o
     ambiente do Colab (ícone de pasta na barra lateral esquerda >
     botão de upload de arquivo).
   - **Via Colab Secrets:** clique no ícone de chave na barra lateral esquerda, adicione um secret chamado
     `GOOGLE_API_KEY` com o valor da sua chave, e habilite o acesso ao
     notebook.
5. Execute as células do notebook **em ordem, de cima para baixo**
   (menu **Ambiente de execução > Executar tudo**, ou célula por célula
   com Shift+Enter).
6. Na última célula, o notebook vai pedir suas perguntas uma a uma no
   próprio output da célula. Digite até 3 perguntas sobre o tema APIs.

## Exemplos de perguntas para testar

- "O que é uma API e para que ela serve?"
- "Qual a diferença entre API REST e SOAP?"
- "O que é um API Gateway e por que ele é usado?"

Experimente também uma pergunta fora do contexto (ex.: "Qual a capital
da França?") para verificar que o bot recusa educadamente e mantém o
foco no tema APIs. Ao final da 3ª resposta, o bot fornece um resumo da
conversa e encerra a sessão automaticamente.
