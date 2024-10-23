# 📄 Tradutor de Artigos Técnicos com AzureAI  

## **Descrição do Projeto**  
Este projeto tem como objetivo desenvolver um **tradutor automático de artigos técnicos** utilizando o **Azure OpenAI**. A solução busca garantir **precisão terminológica e adaptação ao contexto técnico**, facilitando o acesso a conteúdos especializados em múltiplos idiomas.  

A proposta é utilizar o **GPT-4** da Azure OpenAI para tradução, com foco em manter a coerência entre termos técnicos e adaptar-se ao **domínio do conhecimento** (como TI, engenharia ou medicina).  

---

## **📋 Pré-requisitos**  
- **Conta no Azure** com acesso à API do Azure OpenAI  
- **Python 3.x** instalado  
- **Bibliotecas Python:** `openai`, `requests`, `dotenv`  
- **Chave de API e endpoint** do serviço Azure OpenAI

---

## **⚙️ Configuração do Ambiente**

### 1. Criando uma Conta e Configurando o Azure OpenAI  
1. Acesse o [Portal do Azure](https://portal.azure.com) e crie um recurso do **Azure OpenAI**.  
2. Obtenha o **endpoint** e a **chave da API** após configurar o modelo GPT-4.  
3. Registre uma aplicação com permissões de acesso ao serviço OpenAI.

---

### 2. Instalando Dependências  
Execute o seguinte comando para instalar as bibliotecas necessárias:  
bash
pip install openai requests python-dotenv

---

### 3. Estrutura do Projeto  
Crie a seguinte estrutura de pastas e arquivos:

"📁 tradutor-tecnico-azure
│
├── 📄 README.md
├── 📄 .env
├── 📄 tradutor.py
└── 📁 artigos
└── 📄 exemplo_artigo.txt"

---

## 4. Configuração do Arquivo .env  
Adicione o endpoint e a chave de API no arquivo `.env` da seguinte forma:

AZURE_OPENAI_ENDPOINT="https://seu-endpoint.openai.azure.com/"
AZURE_OPENAI_KEY="sua-chave-api"

---

## 🚀 Implementação do Tradutor Técnico  
### Código em Python (arquivo `tradutor.py`)  
```python
import openai
import requests
import os
from dotenv import load_dotenv

# Carregar as variáveis de ambiente
load_dotenv()

# Configurações da API Azure OpenAI
AZURE_OPENAI_ENDPOINT = os.getenv("AZURE_OPENAI_ENDPOINT")
AZURE_OPENAI_KEY = os.getenv("AZURE_OPENAI_KEY")

# Função para traduzir texto com precisão terminológica
def traduzir_texto(texto, idioma_destino="pt"):
    prompt = f"Traduza o seguinte artigo técnico para {idioma_destino}, garantindo precisão nos termos técnicos:\n\n{texto}"

    response = openai.Completion.create(
        engine="gpt-4",  # Use o modelo GPT-4 do Azure
        prompt=prompt,
        max_tokens=1500,
        temperature=0.3
    )

    return response.choices[0].text.strip()

# Função principal: carregar e traduzir um artigo
def traduzir_arquivo(arquivo_path, idioma_destino="pt"):
    with open(arquivo_path, "r", encoding="utf-8") as f:
        conteudo = f.read()
    
    traducao = traduzir_texto(conteudo, idioma_destino)
    return traducao

# Exemplo de uso: traduzir um artigo técnico
if __name__ == "__main__":
    caminho_artigo = "artigos/exemplo_artigo.txt"
    idioma = "en"  # Traduzir para inglês

    print(f"Traduzindo o artigo '{caminho_artigo}' para '{idioma}'...\n")
    resultado = traduzir_arquivo(caminho_artigo, idioma)
    print("Tradução Completa:\n", resultado)

----

##📄 Exemplo de Uso
1. Adicione um artigo técnico para tradução
Crie o arquivo exemplo_artigo.txt dentro da pasta artigos e insira o seguinte conteúdo:

Título: Introdução ao Machine Learning  
O Machine Learning é um campo da inteligência artificial que utiliza algoritmos para aprender com dados e fazer previsões...
2. Execute o script Python:
bash
Copiar código
python tradutor.py
A saída será semelhante a:

vbnet
Copiar código
Traduzindo o artigo 'artigos/exemplo_artigo.txt' para 'en'...

Translation Complete:
Title: Introduction to Machine Learning
Machine Learning is a field of artificial intelligence that uses algorithms to learn from data and make predictions...
🛠 Personalizações Futuras
Domínio Específico: Adicionar ajustes para tradução em áreas como medicina, engenharia ou direito.
Interface Web: Implementar uma interface com Flask ou Django para facilitar o uso.
Detecção Automática de Idioma: Usar a API Text Analytics do Azure para detectar o idioma de entrada.
📌 Contribuições
Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou enviar um pull request.

📄 Licença
Este projeto está licenciado sob a MIT License - consulte o arquivo LICENSE para mais detalhes.

📂 Como Clonar e Executar Localmente
bash
Copiar código
git clone https://github.com/seu-usuario/tradutor-tecnico-azure.git  
cd tradutor-tecnico-azure  
python tradutor.py  
