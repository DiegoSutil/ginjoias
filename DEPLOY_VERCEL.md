# Guia de Deploy: Gin Pratas na Vercel

**Data:** 04 de Dezembro de 2025

---

## Introdução

Este guia detalha o processo passo a passo para publicar seu site **Gin Pratas** na [Vercel](https://vercel.com), uma plataforma de nuvem otimizada para sites estáticos e Jamstack. A Vercel oferece um plano gratuito generoso, deploys automáticos a cada alteração no código e um desempenho excelente.

---

## Pré-requisitos

Antes de começar, você precisará de:

1.  **Conta no GitHub:** Se não tiver, crie uma gratuitamente em [github.com](https://github.com).
2.  **Conta na Vercel:** Se não tiver, crie uma gratuitamente em [vercel.com](https://vercel.com) (você pode usar sua conta do GitHub para se inscrever).
3.  **O arquivo `gin-pratas-corrigido.zip`** que eu te enviei anteriormente.

---

## Passo a Passo para o Deploy

### Passo 1: Crie um Repositório no GitHub

1.  Acesse sua conta no GitHub.
2.  Clique no ícone **+** no canto superior direito e selecione **"New repository"**.
3.  Dê um nome ao seu repositório (ex: `gin-pratas-site`).
4.  Pode deixá-lo como **Público** ou **Privado**.
5.  **NÃO** marque nenhuma das opções como "Add a README file", "Add .gitignore" ou "Choose a license", pois já preparei esses arquivos para você.
6.  Clique em **"Create repository"**.

### Passo 2: Envie os Arquivos do Site para o GitHub

1.  Descompacte o arquivo `gin-pratas-corrigido.zip` em uma pasta no seu computador.
2.  Na página do seu novo repositório no GitHub, clique em **"uploading an existing file"**.
3.  Arraste **todos os arquivos e pastas** de dentro da pasta `gin-pratas` para a área de upload do GitHub.
4.  Aguarde o upload de todos os arquivos.
5.  No campo "Commit changes", escreva uma mensagem como `Versão inicial do site`.
6.  Clique em **"Commit changes"**.

### Passo 3: Importe o Projeto para a Vercel

1.  Acesse seu painel na [Vercel](https://vercel.com/dashboard).
2.  Clique em **"Add New..."** e selecione **"Project"**.
3.  Na seção "Import Git Repository", encontre o repositório que você acabou de criar no GitHub (ex: `gin-pratas-site`) e clique em **"Import"**.

### Passo 4: Configure o Projeto na Vercel

A Vercel é inteligente e deve detectar a configuração correta automaticamente, mas vamos confirmar.

1.  **Framework Preset:** A Vercel deve identificar como **"Other"**. Isso está correto, pois é um site estático.
2.  **Build and Output Settings:** Abra esta seção e verifique se as configurações estão em branco. **Nenhum comando de build é necessário**.
3.  **Environment Variables (Variáveis de Ambiente):** Esta é a parte **mais importante** para a segurança e funcionamento do seu site!

    - No seu código, o arquivo `firebase-config.js` contém suas chaves de API do Firebase. **Não é seguro** deixá-las expostas no código.
    - Vamos movê-las para as variáveis de ambiente da Vercel.

    - No arquivo `firebase-config.js`, você encontrará algo como:
      ```javascript
      const firebaseConfig = {
        apiKey: "SUA_API_KEY",
        authDomain: "SEU_AUTH_DOMAIN",
        // ... e assim por diante
      };
      ```

    - Na Vercel, adicione uma variável de ambiente para **cada uma** das chaves. O nome da variável na Vercel deve começar com `VITE_` para que o código possa acessá-la.

| Nome da Variável na Vercel | Valor (copie do seu `firebase-config.js`) |
| :--- | :--- |
| `VITE_FIREBASE_API_KEY` | O valor de `apiKey` |
| `VITE_FIREBASE_AUTH_DOMAIN` | O valor de `authDomain` |
| `VITE_FIREBASE_PROJECT_ID` | O valor de `projectId` |
| `VITE_FIREBASE_STORAGE_BUCKET` | O valor de `storageBucket` |
| `VITE_FIREBASE_MESSAGING_SENDER_ID` | O valor de `messagingSenderId` |
| `VITE_FIREBASE_APP_ID` | O valor de `appId` |

### Passo 5: Modifique o `firebase-config.js`

Após configurar as variáveis na Vercel, você precisa modificar o arquivo `firebase-config.js` para usá-las. Substitua o conteúdo do arquivo por este:

```javascript
// firebase-config.js

// As variáveis de ambiente são injetadas pela Vercel durante o deploy.
// Para desenvolvimento local, você pode criar um arquivo .env.local
const firebaseConfig = {
  apiKey: import.meta.env.VITE_FIREBASE_API_KEY,
  authDomain: import.meta.env.VITE_FIREBASE_AUTH_DOMAIN,
  projectId: import.meta.env.VITE_FIREBASE_PROJECT_ID,
  storageBucket: import.meta.env.VITE_FIREBASE_STORAGE_BUCKET,
  messagingSenderId: import.meta.env.VITE_FIREBASE_MESSAGING_SENDER_ID,
  appId: import.meta.env.VITE_FIREBASE_APP_ID
};

// Se as variáveis não estiverem definidas (ex: em ambiente local sem .env),
// o app pode não funcionar, o que é esperado.
if (!firebaseConfig.apiKey) {
  console.error("Configuração do Firebase não encontrada! Verifique suas variáveis de ambiente.");
}

export { firebaseConfig };
```

**IMPORTANTE:** Após modificar o `firebase-config.js`, **envie a alteração para o GitHub**. A Vercel irá detectar a mudança e iniciar um novo deploy automaticamente.

### Passo 6: Deploy!

1.  Após configurar as variáveis de ambiente, clique no botão **"Deploy"** na Vercel.
2.  A Vercel irá construir e publicar seu site. O processo leva cerca de 1 minuto.
3.  Ao final, você receberá uma URL pública (ex: `gin-pratas-site.vercel.app`).

---

## Pós-Deploy

🎉 **Parabéns! Seu site está no ar!**

- **Domínio Personalizado:** Você pode ir nas configurações do projeto na Vercel e adicionar seu próprio domínio (ex: `ginpratas.com.br`).
- **Deploys Automáticos:** Sempre que você enviar uma alteração para o seu repositório no GitHub, a Vercel fará o deploy de uma nova versão automaticamente.

Se tiver qualquer dúvida, pode me perguntar!
