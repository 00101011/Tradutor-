# 📄 Tradutor de Artigos Técnicos com AzureAI  

## **Descrição do Projeto**  
Este projeto tem como objetivo desenvolver um **tradutor automático de artigos técnicos** utilizando o **Azure OpenAI**. A solução busca garantir **precisão terminológica e adaptação ao contexto técnico**, facilitando o acesso a conteúdos especializados em múltiplos idiomas. A proposta é utilizar o **GPT-4** da Azure OpenAI para tradução, com foco em manter a coerência entre termos técnicos e adaptar-se ao **domínio do conhecimento** (como TI, engenharia ou medicina).  

---

## **📋 Pré-requisitos**  
- **Conta no Azure** com acesso à API do Azure OpenAI  
- **Python 3.x** instalado  
- **Bibliotecas Python:** `openai`, `requests`, `python-dotenv`  
- **Chave de API e endpoint** do serviço Azure OpenAI

---

## **⚙️ Configuração do Ambiente**

### 1. Criando uma Conta e Configurando o Azure OpenAI  
1. Acesse o [Portal do Azure](https://portal.azure.com) e crie um recurso do **Azure OpenAI**.  
2. Obtenha o **endpoint** e a **chave da API** após configurar o modelo GPT-4.  
3. Registre uma aplicação com permissões de acesso ao serviço OpenAI.

### 2. Instalando Dependências  
Execute o seguinte comando para instalar as bibliotecas necessárias:  
```bash
pip install openai requests python-dotenv
