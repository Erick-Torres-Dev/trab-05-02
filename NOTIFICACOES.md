# Guia de Configuração: Notificações e Secrets

Este guia explica como configurar notificações para sua pipeline CI/CD.

## 📧 Configurando Email (Opcional)

### Passo 1: Criar os Secrets no GitHub

1. Vá para `Settings` → `Secrets and variables` → `Actions`
2. Clique em `New repository secret` e adicione:

```
MAIL_SERVER: seu-servidor-smtp.com
MAIL_PORT: 587
MAIL_USERNAME: seu-email@gmail.com
MAIL_PASSWORD: sua-senha-de-app
MAIL_FROM: seu-email@gmail.com
MAIL_TO: seu-email@gmail.com
```

### Gmail SMTP Configuration

Para Gmail, use:
- **MAIL_SERVER**: smtp.gmail.com
- **MAIL_PORT**: 587
- **MAIL_USERNAME**: seu-email@gmail.com
- **MAIL_PASSWORD**: Gerar App Password em https://myaccount.google.com/apppasswords

## 🤖 Configurando Discord Webhook (Recomendado)

### Passo 1: Criar um Webhook no Discord

1. Abra seu servidor Discord
2. Vá em `Server Settings` → `Integrations` → `Webhooks`
3. Clique em `New Webhook`
4. Configure o nome como "GitHub Actions"
5. Copie a URL do webhook

### Passo 2: Adicionar o Secret no GitHub

1. Vá para `Settings` → `Secrets and variables` → `Actions`
2. Clique em `New repository secret`
3. Nome: `DISCORD_WEBHOOK`
4. Valor: Cole a URL do webhook

## 🔔 Como as Notificações Funcionam

### ✅ Sucesso
- Uma mensagem verde é enviada ao Discord
- Um email é enviado informando sucesso

### ❌ Falha
- Uma mensagem vermelha é enviada ao Discord
- Um email é enviado alertando sobre o erro

## 📝 Utilizando a Pipeline com Notificações

Para usar o arquivo `cd-com-notificacoes.yml`, simplesmente:

1. Certifique-se de que os secrets estão configurados
2. O arquivo já está em `.github/workflows/`
3. Faça um push para `main`
4. Aguarde a notificação no Discord ou Email

## 🧪 Testando as Notificações

Para testar sem fazer deploy real:

1. Crie uma branch de teste
2. Faça uma alteração simples
3. Abra um Pull Request
4. Veja as notificações de CI

## ⚙️ Alternativas de Notificação

### Slack
```yaml
- name: Notificar no Slack
  uses: slackapi/slack-github-action@v1
  with:
    webhook-url: ${{ secrets.SLACK_WEBHOOK }}
    payload: |
      {
        "text": "Deploy realizado com sucesso!",
        "blocks": [...]
      }
```

### Microsoft Teams
```yaml
- name: Notificar no Teams
  uses: jdcargile/ms-teams-notification@v1.3
  with:
    github-token: ${{ github.token }}
    ms-teams-webhook-uri: ${{ secrets.TEAMS_WEBHOOK }}
    notification-color: 28a745
```

## 📞 Suporte

Para mais informações, consulte:
- GitHub Actions Docs: https://docs.github.com/en/actions
- Discord Webhooks: https://discord.com/developers/docs/resources/webhook
- Gmail SMTP: https://support.google.com/mail/answer/7126229
