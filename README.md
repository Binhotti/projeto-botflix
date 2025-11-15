# 🤖 BotFlix

Bem-vindo ao BotFlix! Um simples recomendador de filmes baseado no seu humor.

## 🎬 Sobre o Projeto

O BotFlix é uma aplicação web frontend que permite aos usuários obterem uma sugestão de filme com base no sentimento ou humor que eles descrevem em um campo de texto.

## ✨ Funcionalidades

- Interface simples e intuitiva.
- Campo de texto para descrever seu humor.
- Exibição do filme recomendado com pôster, título, descrição e avaliação.

## ⚙️ Como Funciona

A arquitetura deste projeto é baseada em um frontend que se comunica com um workflow de automação (backend).

1.  **Frontend:** A página web (construída com HTML, CSS e JavaScript) captura o humor digitado pelo usuário.
2.  **Comunicação:** Uma requisição `POST` é enviada para um webhook.
3.  **Backend (n8n):** O webhook é um workflow na plataforma [n8n](https://n8n.io/). Este workflow é responsável por:
    - Receber o humor do usuário.
    - Processar essa informação (por exemplo, usando IA para interpretar o sentimento).
    - Buscar um filme correspondente em uma API de filmes (como a do The Movie Database - TMDB).
    - Retornar os dados do filme sugerido para o frontend.
4.  **Exibição:** O frontend recebe os dados do filme e os exibe na tela.

## 🚀 Começando

Para executar este projeto, você precisará configurar o frontend e o backend (seu workflow n8n).

### Pré-requisitos

- Um workflow n8n ativo e acessível via URL (webhook). O workflow deve ser capaz de receber um JSON com a chave `userPrompt` e retornar os dados de um filme.

### Instalação

1.  Clone este repositório:
    ```bash
    git clone <url-do-repositorio>
    ```
2.  Navegue até o diretório do projeto.

### Configuração

1.  Abra o arquivo `src/js/index.js`.
2.  Encontre a seguinte linha:
    ```javascript
    const response = await fetch('https://binhotti.app.n8n.cloud/webhook-test/botflix', {
    ```
3.  Substitua a URL `'https://binhotti.app.n8n.cloud/webhook-test/botflix'` pela URL do seu próprio webhook do n8n.
4.  Salve o arquivo.

### Executando

Abra o arquivo `index.html` em seu navegador de preferência.

## 📁 Estrutura do Projeto

```
/
├── index.html                # Página principal
├── README.md                 # Este arquivo
└── src/
    ├── css/
    │   ├── animations.css    # Animações
    │   ├── reset.css         # Reset de estilos CSS
    │   ├── responsivo.css    # Estilos para responsividade
    │   └── styles.css        # Estilos principais
    ├── images/
    │   └── botflix-robot.jpg # Imagem usada na página
    └── js/
        └── index.js          # Lógica principal do frontend
```

---
Feito com ❤️ por Vitor Binhotti
