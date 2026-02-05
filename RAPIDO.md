# ⚡ GUIA RÁPIDO - 5 Minutos para Começar

Se você quer ir direto ao ponto, siga este guia rápido!

## 🚀 Passo 1: Criar Repositório (2 min)

```bash
# No GitHub.com
1. Clique em Profile → New repository
2. Nome: seu-nome-seu-repositorio
3. Marque: "Public" ⭐
4. Criar!
```

## 📥 Passo 2: Upload do Projeto (1 min)

```bash
# No seu computador
git clone https://github.com/seu-usuario/seu-repositorio.git
cd seu-repositorio

# Copie TODOS os arquivos deste projeto para lá
# (incluindo .github, images, js, *.html, *.css, *.md)

git add .
git commit -m "Portfólio com CI/CD"
git push origin main
```

## ⚙️ Passo 3: GitHub Pages (1 min)

```
No GitHub:
1. Settings → Pages
2. Source: Deploy from a branch
3. Branch: main, Folder: / (root)
4. Save
```

## 🧪 Passo 4: Testar Falha (30s)

```bash
# Terminal:
git checkout -b teste-falha
rm index.html
git commit -am "Remove index"
git push origin teste-falha

# GitHub:
1. Abrir Pull Request
2. Veg a CI falhar (vermelho) 🔴
3. Fechar PR sem merge
```

## ✅ Passo 5: Testar Sucesso (30s)

```bash
# Terminal:
git checkout main
git pull origin main
git checkout -b teste-ok
echo "<!-- Teste OK -->" >> index.html
git commit -am "Add test"
git push origin teste-ok

# GitHub:
1. Abrir PR
2. Veg a CI passar (verde) ✅
3. Clique "Merge pull request"
4. Aguarde CD (2-3 min)
5. Site estará em: seu-usuario.github.io/seu-repositorio
```

## 📸 Tire Screenshots

1. ❌ Print da CI falhando
2. ✅ Print do Deploy bem-sucedido
3. 🌐 Print do site funcionando

## 📝 Pronto!

- ✅ Portfólio online
- ✅ Pipeline funcionando
- ✅ Proteção de branch
- ✅ Deploy automático

---

**Total: 5-10 minutos!** ⚡

Para detalhes completos, leia os outros arquivos .md
