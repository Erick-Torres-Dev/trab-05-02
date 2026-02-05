[![CI - Validação de Pull Request](https://github.com/seu-usuario/seu-repositorio/actions/workflows/ci.yml/badge.svg)](https://github.com/seu-usuario/seu-repositorio/actions/workflows/ci.yml)
[![CD - Deploy no GitHub Pages](https://github.com/seu-usuario/seu-repositorio/actions/workflows/cd.yml/badge.svg)](https://github.com/seu-usuario/seu-repositorio/actions/workflows/cd.yml)

# Portfólio Profissional - Erick Torres

Bem-vindo ao meu portfólio profissional! Este projeto foi desenvolvido como um trabalho prático de CI/CD no GitHub Actions, demonstrando a implementação completa de uma pipeline de automação profissional.

## 👤 Sobre Mim

**Erick Torres**
- 📅 Idade: 25 anos
- 💼 Posição: Estagiário em TI
- 🎓 Formação: Tecnólogo em Tecnologia da Informação (em andamento)
- ⚙️ Experiência: 10 anos em Hardware | 2 anos em Software

## 🎯 Objetivo

Especializar-me em automação de processos, infraestrutura como código (IaC) e CI/CD, combinando minha vasta experiência em hardware com conhecimentos em desenvolvimento de software.

## 📋 Habilidades Técnicas

### Hardware
- Montagem e manutenção de computadores
- Diagnóstico e resolução de falhas
- Configuração de redes locais (LAN)
- Suporte a impressoras e periféricos
- Windows/Linux - Sistemas Operacionais

### Software & Desenvolvimento
- HTML5 e CSS3
- JavaScript
- Git e GitHub
- Linux Shell Scripting
- Noções de Python

### DevOps & Automação
- GitHub Actions
- CI/CD Pipelines
- Automação de testes
- Linters e validação de código
- GitHub Pages

## 🚀 Pipeline CI/CD

Este projeto implementa uma pipeline de automação completa com as seguintes etapas:

### ✅ Validação Contínua (CI)

A pipeline de CI é disparada em cada Pull Request e valida:

1. **Verificação de index.html** - Garante que o arquivo obrigatório existe na raiz
2. **Validação de nomes de arquivo** - Rejeita arquivos como index-teste.html ou home.html
3. **Limite de tamanho de arquivo** - Bloqueia arquivos maiores que 500KB
4. **Varredura de comentários** - Remove TODO, FIXME e termos sensíveis (senha, password)
5. **Validação de links** - Verifica se as tags img e a possuem URLs válidas
6. **Linting de HTML** - Executa HTMLHint para garantir código de qualidade
7. **Matrix Strategy** - Testa em Node.js 18 e 20 simultaneamente

### 🚢 Deploy Automático (CD)

Após aprovação do PR e merge para main:

1. **Build automático** - Prepara os arquivos
2. **Deploy no GitHub Pages** - Publica o site automaticamente
3. **Notificações** - Informa sucesso ou falha da automação

## 📁 Estrutura do Projeto

```
.
├── index.html                 # Página principal (obrigatório)
├── style.css                  # Estilos da aplicação
├── js/
│   └── main.js               # Scripts JavaScript
├── images/                    # Pasta de imagens
│   ├── perfil.jpg
│   ├── projeto-1.jpg
│   ├── projeto-2.jpg
│   └── projeto-3.jpg
├── .github/
│   └── workflows/
│       ├── ci.yml            # Pipeline de Integração Contínua
│       └── cd.yml            # Pipeline de Entrega Contínua
├── README.md                 # Este arquivo
└── .gitignore               # Arquivos ignorados pelo Git
```

## 🔧 Como Usar

### 1. Clonar o repositório

```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
cd seu-repositorio
```

### 2. Abrir localmente

Abra o arquivo `index.html` no navegador ou use um servidor local:

```bash
# Usando Python
python -m http.server 8000

# Ou usando Node.js (http-server)
npx http-server
```

### 3. Fazer alterações

Crie uma branch para suas modificações:

```bash
git checkout -b feature/minha-mudanca
```

### 4. Submeter Pull Request

Faça push da sua branch e abra um PR:

```bash
git push origin feature/minha-mudanca
```

A pipeline de CI será acionada automaticamente!

## 📊 Status da Pipeline

| Workflow | Status | Link |
|----------|--------|------|
| CI (Validação) | [![CI - Validação de Pull Request](https://github.com/seu-usuario/seu-repositorio/actions/workflows/ci.yml/badge.svg)](https://github.com/seu-usuario/seu-repositorio/actions/workflows/ci.yml) | [Actions](https://github.com/seu-usuario/seu-repositorio/actions) |
| CD (Deploy) | [![CD - Deploy no GitHub Pages](https://github.com/seu-usuario/seu-repositorio/actions/workflows/cd.yml/badge.svg)](https://github.com/seu-usuario/seu-repositorio/actions/workflows/cd.yml) | [Actions](https://github.com/seu-usuario/seu-repositorio/actions) |

## 🌐 Acessar o Site

O site está disponível em: **[seu-repositorio.github.io](https://seu-usuario.github.io/seu-repositorio)**

## 📱 Redes Sociais

- 🐙 [GitHub](https://github.com)
- 💼 [LinkedIn](https://linkedin.com)
- 📷 [Instagram](https://instagram.com)
- 📧 Email: erick@example.com

## 🔐 Configurações de Segurança

### Branch Protection Rules

As seguintes regras foram configuradas para proteger a branch `main`:

- ✅ Exigir Pull Request Reviews antes de merge
- ✅ Descartar stale review após push
- ✅ Exigir que a CI passe antes de merge
- ✅ Desabilitar merge sem revisor

## 📚 Aprendizados

Este projeto me permitiu aprender e aplicar:

- Automação de workflows com GitHub Actions
- Boas práticas de CI/CD
- Validação de código automatizada
- Deploy contínuo em GitHub Pages
- Matrix strategy para testes em múltiplas versões
- Proteção de branches e code review

## 🎓 Trabalho Prático

Este é um trabalho prático da disciplina de **"Esteira de Produção (CI/CD)"** onde implementei:

1. ✅ Proteção de Branch (CI)
2. ✅ Publicação Automática (CD)
3. ✅ Badge de Status
4. ✅ Notificações (log output)
5. ✅ Matrix Strategy (Node 18 e 20)

## 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.

## 👥 Colaboradores

- **09116428-collab** - Colaborador designado

## 📧 Contato

Não hesite em entrar em contato para dúvidas ou oportunidades profissionais!

---

**Desenvolvido com ❤️ por Erick Torres**
*Portfólio e Automação CI/CD | 2026*
