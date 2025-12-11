# Queer Rights - Site da Comunidade

Site estático hospedado no GitHub Pages usando Jekyll para apresentar a comunidade Queer Rights.

## 🌈 Sobre

Este site apresenta a comunidade Queer Rights, dedicada à luta pelos direitos LGBTQIA+. O site inclui informações sobre a comunidade, valores e um botão para entrar no grupo Signal.

## 🚀 Configuração

### Pré-requisitos

- Ruby (versão 2.7 ou superior)
- Bundler (`gem install bundler`)

### Instalação Local

1. Clone o repositório:
```bash
git clone <seu-repositorio>
cd <diretorio-do-repositorio>
```

2. Instale as dependências:
```bash
bundle install
```

3. Execute o servidor local:
```bash
bundle exec jekyll serve
```

4. Acesse o site em `http://localhost:4000`

## 📝 Configuração do Link do Signal

**IMPORTANTE:** Você precisa substituir o link do grupo Signal no arquivo `index.html`:

1. Abra o arquivo `index.html`
2. Encontre a linha com o link:
```html
<a href="https://signal.group/#YOUR_GROUP_LINK" 
```
3. Substitua `YOUR_GROUP_LINK` pelo link real do seu grupo Signal
4. Remova a nota de aviso após configurar o link

## 🌐 Publicação no GitHub Pages

### Método 1: Branch `gh-pages`

1. Faça commit das alterações:
```bash
git add .
git commit -m "Site inicial da comunidade Queer Rights"
```

2. Crie a branch `gh-pages`:
```bash
git checkout -b gh-pages
git push origin gh-pages
```

3. No GitHub, vá em Settings > Pages e configure para usar a branch `gh-pages`

### Método 2: GitHub Actions (Recomendado)

1. Crie o arquivo `.github/workflows/jekyll.yml`:
```yaml
name: Jekyll site CI

on:
  push:
    branches:
      - main
  pull_request:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: ruby/setup-ruby@v1
        with:
          ruby-version: '3.1'
          bundler-cache: true
      - run: bundle exec jekyll build
      - uses: actions/upload-pages-artifact@v1
      - uses: actions/deploy-pages@v1
```

2. No GitHub, vá em Settings > Pages e configure para usar GitHub Actions

## 📁 Estrutura do Projeto

```
.
├── _config.yml          # Configurações do Jekyll
├── _layouts/            # Templates HTML
│   └── default.html     # Layout base
├── assets/              # Arquivos estáticos
│   └── css/
│       └── style.css    # Estilos do site
├── index.html           # Página principal
├── Gemfile              # Dependências Ruby
├── .gitignore           # Arquivos ignorados pelo Git
└── README.md            # Este arquivo
```

## 🎨 Personalização

- **Cores e estilos**: Edite `assets/css/style.css`
- **Conteúdo**: Edite `index.html`
- **Configurações**: Edite `_config.yml`

## 📱 Recursos

- ✅ Design responsivo (mobile-friendly)
- ✅ Cores inspiradas na bandeira LGBTQIA+
- ✅ Botão para entrar no grupo Signal
- ✅ Seções sobre valores e missão da comunidade
- ✅ Pronto para GitHub Pages

## 🤝 Contribuindo

Sinta-se à vontade para fazer fork, melhorar e contribuir com o projeto!

## 📄 Licença

Este projeto é livre para uso pela comunidade.

---

Feito com ❤️ pela comunidade Queer Rights
