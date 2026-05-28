# 🔔 Como ativar as Notificações Push — Barbearia 09

O site agora tem **3 camadas de notificação** pra você nunca perder um agendamento:

1. **Painel** → o agendamento sempre aparece lá (garantia total)
2. **WhatsApp (CallMeBot)** → mensagem no zap (já configurado)
3. **Push na tela** → notificação no celular tipo app (configurar abaixo)

---

## ⚙️ PASSO ÚNICO — Configurar as chaves na Netlify

As notificações push precisam de 2 "chaves de segurança" (VAPID). Eu já gerei elas
pra você. Você só precisa colá-las na Netlify uma vez:

### As suas chaves:

```
VAPID_PUBLIC
BCEFVi6YOwvf-vXHfsRmPHahwOgi0hemWG-_D_6bTrmeyaIYb_rZY7qwW7i2KNMjdkao5jWPHVSeqTvZuMhE-tk

VAPID_PRIVATE
Z1uCC1OqMFsaNBrQqtqxGfUfTPnDgAjjpJk9Mp9Z_DE
```

### Onde colar:

1. Entre em https://app.netlify.com e abra seu site
2. Vá em **Site configuration** (ou "Site settings")
3. No menu, clique em **Environment variables**
4. Clique em **Add a variable** → **Add a single variable**
5. Adicione a primeira:
   - **Key**: `VAPID_PUBLIC`
   - **Value**: cole a chave pública acima (a longa)
   - Salve
6. Adicione a segunda:
   - **Key**: `VAPID_PRIVATE`
   - **Value**: cole a chave privada acima (a curta)
   - Salve
7. Vá em **Deploys** → **Trigger deploy** → **Deploy site** (pra aplicar as chaves)

Pronto! O servidor de push está configurado.

---

## 📱 COMO O BARBEIRO ATIVA (em cada celular)

Em **cada celular** que o barbeiro for usar:

### No Android (funciona melhor)
1. Abra `seu-site.netlify.app/admin`
2. Faça login
3. Vá na aba **Configurações**
4. No card "🔔 Notificações neste celular", toque em **Ativar notificações**
5. Aceite a permissão que aparecer
6. Pronto! Aparece "✅ Notificações ATIVAS"

### No iPhone (precisa de um passo extra)
O iPhone só permite notificação de site se ele estiver "instalado":
1. Abra `seu-site.netlify.app/admin` no **Safari**
2. Toque no botão **Compartilhar** (quadrado com seta pra cima)
3. Escolha **"Adicionar à Tela de Início"**
4. Agora abra o site **pelo ícone** que apareceu na tela (não pelo Safari)
5. Faça login → aba **Configurações** → **Ativar notificações**
6. Aceite a permissão

> ⚠️ No iPhone, a notificação de site é menos garantida que no Android.
> Por isso mantemos também o aviso por WhatsApp e o painel como garantia.

---

## ✅ COMO TESTAR

1. Ative a notificação num celular (passos acima)
2. De outro aparelho (ou aba anônima), faça um agendamento de teste
3. A notificação deve aparecer na tela do celular ativado

---

## 💡 IMPORTANTE — A regra de ouro

Mesmo com tudo isso, oriente o barbeiro a **abrir o painel de manhã e à tarde**.
O painel SEMPRE tem todos os agendamentos, mesmo que uma notificação falhe.
Isso garante que nenhum agendamento passe batido.

---

Desenvolvido por **HugoDevWeb** — https://hugodevweb.netlify.app/
