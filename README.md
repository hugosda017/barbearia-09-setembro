# Barbearia 09 de Setembro — Site Completo

Site com agendamento online, painel administrativo e **banco de dados real**.
Os agendamentos sincronizam automaticamente entre todos os celulares.

---

## 🎯 O QUE MUDOU (versão completa)

Agora o site tem um **backend de verdade** usando recursos gratuitos da
própria Netlify:
- **Netlify Functions** → o "servidor" do site
- **Netlify Blobs** → o banco de dados (grátis, sem configurar nada)

Resultado: cliente agenda no celular → barbeiro vê na hora, em qualquer
aparelho. Funciona de verdade. ✅

---

## 📁 ESTRUTURA DO PROJETO

```
barbearia/
├── netlify.toml              → configuração da Netlify
├── package.json              → dependências do backend
├── .gitignore
├── netlify/
│   └── functions/
│       └── data.mjs          → o backend (salva/lê agendamentos)
└── public/                   → o site em si
    ├── index.html            → página principal
    ├── admin.html            → painel administrativo
    ├── config.js             → configurações (telefone, etc)
    ├── cloud-storage.js       → conexão com o banco
    ├── app.js                → lógica do site
    ├── admin.js              → lógica do painel
    └── styles.css            → visual
```

---

## 🚀 COMO HOSPEDAR NA NETLIFY (passo a passo)

Com backend, o site precisa subir via **GitHub**. É de graça e depois
fica automático. Siga na ordem:

### Parte 1 — Subir para o GitHub

**Pelo site do GitHub (sem programa nenhum):**

1. Crie uma conta em https://github.com (se ainda não tiver)
2. Clique em **"New repository"** (botão verde, ou em https://github.com/new)
3. Dê um nome, ex: `barbearia-09-setembro`
4. Deixe como **Public** (ou Private, tanto faz)
5. **NÃO** marque nenhuma opção extra. Clique em **"Create repository"**
6. Na página que abrir, clique no link **"uploading an existing file"**
7. **Arraste TODA a pasta do projeto** (com as subpastas `netlify` e `public`)
   para a área de upload
8. Espere subir tudo e clique em **"Commit changes"**

> ⚠️ Importante: precisa subir as PASTAS (`netlify/` e `public/`), não só
> os arquivos soltos. O upload do GitHub aceita arrastar pastas inteiras.

### Parte 2 — Conectar na Netlify

1. Entre em https://app.netlify.com
2. Clique em **"Add new site"** → **"Import an existing project"**
3. Escolha **"Deploy with GitHub"** e autorize
4. Selecione o repositório `barbearia-09-setembro`
5. Na tela de configuração, confira (geralmente já vem certo):
   - **Build command**: deixe vazio
   - **Publish directory**: `public`
   - **Functions directory**: `netlify/functions`
6. Clique em **"Deploy"**
7. Espere 1-2 minutos. Pronto! O site fica no ar com uma URL própria.

### Parte 3 — Ativar o banco de dados (Netlify Blobs)

O Netlify Blobs **já funciona automaticamente** — não precisa fazer nada.
Na primeira vez que alguém agendar, o banco é criado sozinho.

---

## ✅ COMO TESTAR SE FUNCIONOU

1. Abra o site (a URL que a Netlify deu)
2. Faça um agendamento de teste
3. Abra `sua-url.netlify.app/admin` em **outro celular** (ou outro navegador)
4. Senha padrão: `admin123`
5. O agendamento deve aparecer no painel ✓

Se aparecer em outro aparelho, a sincronização está funcionando!

---

## 🔄 COMO ATUALIZAR O SITE DEPOIS

Toda vez que quiser mudar algo (ex: telefone no `config.js`):

1. No GitHub, abra o arquivo que quer mudar
2. Clique no ícone de lápis (editar)
3. Faça a mudança e clique em **"Commit changes"**
4. A Netlify atualiza o site sozinha em ~1 minuto

---

## ⚙️ CONFIGURAÇÕES (config.js)

Tudo que muda com frequência está em `public/config.js`:
- Telefone e Instagram do barbeiro
- Senha do painel admin
- Horários de funcionamento
- Serviços e preços (a ordem na lista = ordem no site)
- Notificações por WhatsApp (CallMeBot)

---

## 🔔 NOTIFICAÇÕES POR WHATSAPP

Já configurado via CallMeBot. Quando um cliente agenda, o número
cadastrado em `config.js > notifications > recipients` recebe uma
mensagem no WhatsApp com os dados do agendamento.

---

## 🔐 PAINEL ADMINISTRATIVO

- Acesse em: `sua-url.netlify.app/admin`
- Senha padrão: `admin123` (troque no próprio painel)

---

Desenvolvido por **HugoDevWeb** — https://hugodevweb.netlify.app/
