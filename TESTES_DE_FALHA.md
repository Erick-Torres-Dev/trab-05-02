# 🧪 Teste de Falha Intencional da Pipeline

Este arquivo contém exemplos de como testar a falha da pipeline CI/CD.

## 🔴 Como Criar uma Falha Intencional

Para demonstrar que a pipeline está funcionando corretamente (e pode detectar erros), siga os passos abaixo:

### Teste 1: Remover index.html

1. Crie uma branch: `git checkout -b teste-falha-index`
2. Delete o arquivo: `rm index.html`
3. Faça commit: `git commit -am "Remove index.html - TESTE DE FALHA"`
4. Push: `git push origin teste-falha-index`
5. Abra um PR no GitHub
6. A pipeline falhará com: **"Arquivo index.html não encontrado"**

### Teste 2: Renomear index.html

1. Crie uma branch: `git checkout -b teste-falha-rename`
2. Renomeie o arquivo: `mv index.html home.html`
3. Faça commit: `git commit -am "Renomeia index para home - TESTE"`
4. Push: `git push origin teste-falha-rename`
5. A pipeline falhará com: **"Arquivos HTML com nome inválido encontrados"**

### Teste 3: Adicionar comentário TODO

1. Crie uma branch: `git checkout -b teste-falha-TODO`
2. Adicione em index.html:
   ```html
   <!-- TODO: Corrigir essa seção depois -->
   ```
3. Faça commit e push
4. A pipeline falhará com: **"TODO encontrado no código"**

### Teste 4: Adicionar termo sensível "senha"

1. Crie uma branch: `git checkout -b teste-falha-senha`
2. Adicione em um arquivo:
   ```javascript
   // senha: admin123
   ```
3. Faça commit e push
4. A pipeline falhará com: **"Termo 'senha' encontrado"**

### Teste 5: Arquivo muito grande

1. Crie uma imagem com mais de 500KB
2. Adicione ao projeto
3. A pipeline falhará com: **"Arquivo maior que 500KB"**

### Teste 6: Link vazio

1. Crie uma branch: `git checkout -b teste-falha-link`
2. Adicione em index.html:
   ```html
   <a href="">Link vazio</a>
   <img src="" alt="Imagem vazia">
   ```
3. A pipeline falhará com: **"href vazio" ou "src vazio"**

## ✅ Teste de Sucesso

Após confirmar que a pipeline detecta erros, teste um merge bem-sucedido:

1. Crie uma branch: `git checkout -b teste-sucesso`
2. Faça uma alteração válida (ex: atualizar biografia)
3. Push e abra um PR
4. A pipeline passará ✅
5. Clique em "Merge pull request"
6. Aguarde o CD publicar automaticamente 🚀

## 📊 Verificar Status

Para ver o status das pipelines:

1. Vá para a aba **Actions** no GitHub
2. Você verá a lista de workflows executados
3. Clique em um workflow para ver os detalhes
4. Veja os logs passo a passo

## 🎯 O Que Cada Teste Demonstra

| Teste | O que valida |
|-------|-------------|
| Remover index.html | Verificação obrigatória |
| Renomear arquivo | Nomes específicos |
| TODO/FIXME | Limpeza de comentários |
| "senha"/"password" | Segurança |
| Arquivo > 500KB | Otimização |
| Links vazios | Validação de código |

## 💡 Dicas

- Use `git branch -D nome-branch` para deletar branches de teste após concluir
- Todos os testes podem ser feitos sem merging para main
- A pipeline não afeta a branch main, apenas PRs
- Use `git status` para verificar o que foi modificado antes de committar

---

**Desenvolvido para demonstração de CI/CD em GitHub Actions**
