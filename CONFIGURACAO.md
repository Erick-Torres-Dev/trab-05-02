# ⚙️ Guia de Configuração do GitHub

Este arquivo explica como configurar corretamente seu repositório para CI/CD.

## 1️⃣ Criar Repositório no GitHub

### Passo 1: Login e Criar Novo Repositório

1. Acesse [github.com](https://github.com)
2. Clique em **"New"** (novo repositório)
3. Escolha o nome: `seu-nome-seu-repositorio`
4. Descrição: "Portfólio Profissional com CI/CD"
5. Escolha **Public** (para que GitHub Pages funcione)
6. Clique em **"Create repository"**

### Passo 2: Clonar para sua máquina

```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
cd seu-repositorio
```

## 2️⃣ Configurar GitHub Pages

### Passo 1: Acessar Settings

1. Vá para seu repositório
2. Clique na aba **Settings**
3. No menu lateral, procure por **Pages**

### Passo 2: Ativar GitHub Pages

1. Em "Source", selecione:
   - **Deploy from a branch**
   - **Branch**: `main`
   - **Folder**: `/ (root)`
2. Clique em **Save**

## 3️⃣ Proteger a Branch Principal

### Passo 1: Configurar Branch Protection

1. Em **Settings** → **Branches**
2. Clique em "Add rule" ou "Add branch protection rule"
3. Nome do padrão: `main`

### Passo 2: Ativar Proteções

- ✅ **Require a pull request before merging**
- ✅ **Require status checks to pass before merging**
  - Selecione: `validate` (seu job de CI)
- ✅ **Require branches to be up to date before merging**
- ✅ **Require code reviews before merging** (opcional, mas recomendado)
- ✅ **Dismiss stale pull request approvals when new commits are pushed**

## 4️⃣ Adicionar Colaborador

### Passo 1: Ir para Settings → Collaborators

1. Em **Settings** → **Collaborators**
2. Clique em **Add people**
3. Digite o nome de usuário: `09116428-collab`
4. Escolha o nível de acesso: **Maintain** ou **Write**
5. Clique em **Add**

A pessoa receberá um convite por email.

## 5️⃣ Adicionar Secrets para CI/CD

### Para Notificações por Discord

1. Vá para **Settings** → **Secrets and variables** → **Actions**
2. Clique em **New repository secret**
3. Nome: `DISCORD_WEBHOOK`
4. Valor: Cole a URL do webhook do Discord

### Para Notificações por Email

1. Crie em **Secrets**:
   - `MAIL_SERVER`
   - `MAIL_PORT`
   - `MAIL_USERNAME`
   - `MAIL_PASSWORD`
   - `MAIL_FROM`
   - `MAIL_TO`

## 6️⃣ Atualizar URLs nos Badges

No arquivo `README.md`, atualize os badges:

**Encontre:**
```markdown
[![CI - ...](https://github.com/seu-usuario/seu-repositorio/actions/workflows/ci.yml/badge.svg)](...)
```

**Substitua:**
```markdown
[![CI - Validação de Pull Request](https://github.com/SEU_USUARIO_REAL/SEU_REPOSITORIO_REAL/actions/workflows/ci.yml/badge.svg)](https://github.com/SEU_USUARIO_REAL/SEU_REPOSITORIO_REAL/actions/workflows/ci.yml)
```

## 7️⃣ Upload do Projeto

### Passo 1: Adicionar arquivos

```bash
git add .
```

### Passo 2: Commit inicial

```bash
git commit -m "feat: Portfólio profissional com CI/CD

- Estrutura HTML e CSS
- Workflows de automação
- Validações de qualidade
- Deploy automático no GitHub Pages"
```

### Passo 3: Push para main

```bash
git push origin main
```

## 8️⃣ Verificar Execução

1. Vá para a aba **Actions** do seu repositório
2. Você verá o workflow `CD - Deploy no GitHub Pages` executando
3. Aguarde concluir (geralmente 1-2 minutos)
4. Você receberá uma notificação quando estiver pronto

## 9️⃣ Acessar seu Site

Seu site estará disponível em:

```
https://seu-usuario.github.io/seu-repositorio
```

## 🔟 Rotas Úteis

| Função | URL |
|--------|-----|
| Repositório | `https://github.com/seu-usuario/seu-repositorio` |
| Actions | `https://github.com/seu-usuario/seu-repositorio/actions` |
| Settings | `https://github.com/seu-usuario/seu-repositorio/settings` |
| Site ao vivo | `https://seu-usuario.github.io/seu-repositorio` |

## ✅ Checklist de Configuração

- [ ] Repositório criado no GitHub
- [ ] Código enviado (push) para main
- [ ] GitHub Pages ativado
- [ ] Branch main protegida
- [ ] CI executa em PRs
- [ ] CD executa após merge
- [ ] Site está acessível publicamente
- [ ] Colaborador 09116428-collab adicionado
- [ ] Badges atualizadas no README
- [ ] Notificações configuradas (opcional)

## 🆘 Troubleshooting

### GitHub Pages não aparece

- Verifique se o repositório é **Public**
- Aguarde 2-3 minutos após o primeiro deploy
- Vá em Settings → Pages e confirme que está ativado

### CI não roda

- Verifique se os workflows estão em `.github/workflows/`
- Confirme os nomes dos arquivos: `ci.yml` e `cd.yml`
- Verifique a syntax YAML (indentação!)

### Merge desativado

- Isso é intencional! A branch está protegida
- Aguarde o status check passar
- Clique em "Merge pull request"

---

**Configurado e pronto para produção!** 🚀
