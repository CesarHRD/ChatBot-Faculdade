
# ChatBot Trabalho Garantido

Chatbot desenvolvido como projeto acadêmico de Trabalho de Graduação (TG), com o objetivo de facilitar o acesso às informações do edital do Programa Trabalho Garantido.

A aplicação utiliza Inteligência Artificial e a técnica **RAG (Retrieval-Augmented Generation)** para responder às dúvidas dos usuários com base nas informações presentes no documento oficial do edital.

## Sobre o projeto

O ChatBot Trabalho Garantido permite que o usuário faça perguntas em linguagem natural sobre o edital do programa e receba respostas contextualizadas, sem precisar pesquisar manualmente pelo documento.

A solução combina recuperação de informações em documentos PDF com um modelo de linguagem (LLM), tornando a consulta mais simples, rápida e acessível.

## Funcionalidades

- Interface de conversação interativa.
- Leitura e processamento de documentos PDF.
- Busca semântica de informações utilizando embeddings.
- Geração de respostas com Inteligência Artificial.
- Respostas fundamentadas no conteúdo do edital.
- Orientação para informar quando uma resposta não for encontrada no documento.
- Histórico de mensagens durante a sessão.

## Tecnologias utilizadas

| Tecnologia | Finalidade |
|---|---|
| Python | Linguagem principal |
| Streamlit | Interface web do chatbot |
| LangChain | Integração e gerenciamento do fluxo RAG |
| Groq API | Acesso ao modelo de linguagem |
| Hugging Face | Geração de embeddings |
| Sentence Transformers | Modelo de embeddings |
| ChromaDB | Banco de dados vetorial |
| PyPDF | Leitura de documentos PDF |
| python-dotenv | Gerenciamento de variáveis de ambiente |

### Modelos utilizados

- **LLM:** `openai/gpt-oss-120b`
- **Embeddings:** `sentence-transformers/all-MiniLM-L6-v2`
- **Banco vetorial:** ChromaDB

## Como funciona?

O chatbot utiliza a arquitetura RAG (Retrieval-Augmented Generation), seguindo as seguintes etapas:

1. **Carregamento:** o edital em PDF é carregado e seu conteúdo é extraído.
2. **Fragmentação:** o documento é dividido em pequenos trechos (*chunks*), com sobreposição para preservar o contexto.
3. **Embeddings:** os trechos são transformados em representações vetoriais utilizando o Hugging Face.
4. **Armazenamento:** os vetores são armazenados no banco de dados ChromaDB.
5. **Recuperação:** quando o usuário faz uma pergunta, o sistema busca os cinco trechos mais relevantes.
6. **Geração:** os trechos recuperados são enviados como contexto para o modelo de linguagem através da API Groq.
7. **Resposta:** o chatbot apresenta uma resposta baseada nas informações recuperadas do edital.

## Pré-requisitos

Antes de executar o projeto, você precisará ter:

- Python instalado.
- Git instalado.
- Uma chave de API da Groq.
- Acesso à internet para utilizar a API e baixar os modelos necessários.

## Instalação e execução

### 1. Clone o repositório

```bash
git clone https://github.com/CesarHRD/ChatBot-Faculdade.git
```

### 2. Entre na pasta do projeto

```bash
cd ChatBot-Faculdade
```

### 3. Crie um ambiente virtual

```bash
python -m venv venv
```

### 4. Ative o ambiente virtual

**Windows:**

```bash
venv\Scripts\activate
```

**Linux / macOS:**

```bash
source venv/bin/activate
```

### 5. Instale as dependências

```bash
pip install -r requirements.txt
```

### 6. Configure a chave da API Groq

Crie um arquivo chamado `.env` na raiz do projeto:

```env
GROQ_API_KEY=sua_chave_api_aqui
```

Substitua `sua_chave_api_aqui` pela sua chave de API da Groq.

Você pode obter uma chave em:

https://console.groq.com/

**Importante:** nunca compartilhe sua chave de API ou envie o arquivo `.env` para o GitHub.

### 7. Execute a aplicação

```bash
python -m streamlit run app.py
```

Após a inicialização, o Streamlit disponibilizará o endereço local para acessar o chatbot pelo navegador.

## Estrutura do projeto

```text
ChatBot-Faculdade/
│
├── app.py
├── requirements.txt
├── .gitignore
├── EDITAL_Trabalho_Garantido.pdf
├── Dirf2025-Perguntas&Respostas v20241230.pdf
├── Apresentacao_Chatbot_TG.pdf
├── Chatbot TG_estrutura.pdf
└── README.md
```

### Principais arquivos

- **app.py:** código-fonte da aplicação, contendo a interface e a implementação da arquitetura RAG.
- **requirements.txt:** lista de dependências Python necessárias para executar o projeto.
- **EDITAL_Trabalho_Garantido.pdf:** documento utilizado como base de conhecimento do chatbot.
- **Dirf2025-Perguntas&Respostas v20241230.pdf:** documento complementar disponibilizado no repositório.
- **Apresentacao_Chatbot_TG.pdf:** apresentação acadêmica do projeto.
- **Chatbot TG_estrutura.pdf:** documentação relacionada à estrutura do trabalho.

## Segurança

- Armazene a chave da API Groq em variáveis de ambiente.
- Não publique credenciais ou tokens de acesso.
- Mantenha o arquivo `.env` fora do controle de versão.
- Utilize documentos oficiais e atualizados como fonte de conhecimento.

## Objetivo acadêmico

Este projeto foi desenvolvido no contexto de um Trabalho de Graduação (TG), explorando a aplicação de Inteligência Artificial Generativa, processamento de documentos e recuperação aumentada de informações para solucionar um problema prático de acesso à informação.

## Autor

**CesarHRD**

GitHub: https://github.com/CesarHRD

## Licença

Este projeto foi desenvolvido para fins acadêmicos.
