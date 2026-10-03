Sistema web responsivo para gerenciamento visual de catálogo e empréstimos de uma biblioteca, desenvolvido com HTML, CSS e JavaScript.

O **VITALIS Library System** é um projeto front-end que simula a experiência de uma biblioteca digital.  
A aplicação permite visualizar um catálogo de livros, consultar disponibilidade, realizar empréstimos, acompanhar livros ativos no perfil do usuário e devolver itens diretamente pela interface.

O projeto foi desenvolvido com foco em **interface moderna, renderização dinâmica com JavaScript e experiência responsiva**.

---

## ✨ Funcionalidades

### 📖 Catálogo de livros

O sistema apresenta um catálogo visual com os livros disponíveis na biblioteca.

Cada item exibe:

- capa
- título
- autor
- status de disponibilidade
- ação para realizar empréstimo

Os livros são renderizados dinamicamente por JavaScript a partir de uma estrutura de dados interna.

---

### ✅ Controle de disponibilidade

Cada livro possui um status:

```text
Available
Checked Out
```

Ao realizar um empréstimo:

- o livro passa automaticamente para `borrowed`
- o botão de empréstimo é desabilitado
- o status visual é atualizado
- o contador geral de empréstimos é atualizado
- o livro passa a aparecer no perfil do usuário

---

### 📥 Empréstimo de livros

O usuário pode selecionar um livro disponível e clicar em:

```text
Borrow Book
```

O sistema registra automaticamente:

- livro emprestado
- data do empréstimo
- data prevista para devolução

A data de devolução é calculada para **14 dias após o empréstimo**.

---

### 📤 Devolução de livros

Na área de perfil, o usuário pode devolver qualquer livro ativo.

Ao clicar em:

```text
Return
```

o sistema:

- remove o livro da lista de empréstimos ativos
- altera o status do livro novamente para disponível
- atualiza o catálogo
- atualiza o contador de empréstimos

---

### 👤 Perfil do usuário

A aplicação possui uma área específica para o usuário da biblioteca.

Atualmente, o perfil apresenta:

- nome do usuário
- identificação
- empréstimos ativos
- data do empréstimo
- data prevista de devolução
- opção para devolver livros

Quando não existem empréstimos ativos, o sistema mostra um estado vazio com acesso rápido ao catálogo.

---

### 🔄 Navegação dinâmica

A interface possui duas áreas principais:

```text
VITALIS
│
├── 📚 Catalog
│   ├── Catálogo de livros
│   ├── Disponibilidade
│   ├── Empréstimos
│   └── Contador de livros emprestados
│
└── 👤 My Profile
    ├── Dados do usuário
    ├── Empréstimos ativos
    ├── Datas de empréstimo
    ├── Datas de devolução
    └── Retorno de livros
```

A troca entre as telas é realizada com JavaScript, sem necessidade de recarregar a página.

---

## 🛠️ Tecnologias utilizadas

<div>
  <img align="center" alt="HTML5" height="40" width="50" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/html5/html5-original.svg">
  <img align="center" alt="CSS3" height="40" width="50" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/css3/css3-original.svg">
  <img align="center" alt="JavaScript" height="40" width="50" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/javascript/javascript-original.svg">
</div>

<br>

Também são utilizados:

- **JavaScript DOM API**
- **Iconify**
- **Lucide Icons**
- **CSS responsivo**
- **CSS Grid**
- **Flexbox**
- **Animações CSS**
- **Google Fonts / fontes locais**
- **Renderização dinâmica de componentes**
- **Manipulação de estado no front-end**

---

## 🧠 Conceitos aplicados

Durante o desenvolvimento do projeto foram trabalhados conceitos como:

- manipulação do DOM
- arrays e objetos em JavaScript
- alteração de estado da aplicação
- eventos de interface
- funções reutilizáveis
- renderização dinâmica com `map()`
- busca de elementos com `findIndex()`
- atualização de dados em memória
- manipulação de datas
- template literals
- componentes visuais reutilizáveis
- estados vazios
- feedback visual de disponibilidade
- navegação entre views
- responsividade
- experiência do usuário

---

## 🎨 Interface

O VITALIS utiliza uma identidade visual limpa e institucional, com foco em legibilidade e navegação simples.

O projeto inclui:

- catálogo em cards
- grid responsivo
- banner principal
- status visuais
- microinterações
- efeitos de hover
- animações de entrada
- navegação fixa
- layout adaptável para desktop e dispositivos menores

A identidade utiliza principalmente tons de:

```text
Slate
Teal
White
```

---

## ⚙️ Como funciona

A aplicação mantém duas estruturas principais:

```javascript
libraryData
userLoans
```

### `libraryData`

Responsável pelo catálogo de livros e pelo status de disponibilidade de cada item.

### `userLoans`

Armazena os livros atualmente emprestados pelo usuário.

Quando o usuário realiza uma ação, o sistema atualiza essas estruturas e executa novamente:

```javascript
renderApp();
```

Isso mantém catálogo e perfil sincronizados.

---

## 🚀 Como executar

O projeto não exige instalação de dependências ou backend.

### 1. Clone o repositório

```bash
git clone https://github.com/J040P/NOME-DO-REPOSITORIO.git
```

### 2. Entre na pasta

```bash
cd NOME-DO-REPOSITORIO
```

### 3. Abra o projeto

Abra o arquivo principal:

```text
index.html
```

em seu navegador.

Também é possível executar utilizando a extensão **Live Server** no VS Code.

---

## 📂 Estrutura do projeto

A estrutura pode variar conforme os arquivos exportados, mas a aplicação principal segue aproximadamente:

```text
vitalis/
│
├── index.html
│
├── assets/
│   ├── css/
│   ├── fonts/
│   └── scripts/
│
└── README.md
```

---

## 📊 Fluxo da aplicação

```text
Usuário acessa o sistema
        │
        ▼
Visualiza o catálogo
        │
        ▼
Escolhe um livro disponível
        │
        ▼
Realiza o empréstimo
        │
        ├── status → borrowed
        ├── registra data atual
        └── calcula devolução +14 dias
        │
        ▼
Livro aparece em "My Profile"
        │
        ▼
Usuário devolve o livro
        │
        ├── remove empréstimo
        └── status → available
        │
        ▼
Catálogo é atualizado
```

---

## ⚠️ Estado atual do projeto

A versão atual funciona totalmente no **front-end**.

Os dados de empréstimo são mantidos em memória durante a execução da página.

Isso significa que, ao atualizar ou fechar o navegador, os empréstimos realizados durante a sessão não são preservados.

Não há, nesta versão:

- banco de dados
- autenticação real
- backend
- persistência permanente
- controle real de usuários
- integração com API externa

Esses pontos fazem parte das possibilidades de evolução do projeto.

---

## 🗺️ Roadmap

Próximas melhorias que podem transformar o VITALIS em um sistema mais completo:

- [ ] Adicionar pesquisa de livros
- [ ] Criar filtros por categoria
- [ ] Criar sistema de autenticação
- [ ] Adicionar cadastro de usuários
- [ ] Implementar LocalStorage
- [ ] Criar backend
- [ ] Integrar banco de dados
- [ ] Implementar API REST
- [ ] Criar painel administrativo
- [ ] Adicionar cadastro e edição de livros
- [ ] Controlar quantidade de exemplares
- [ ] Criar sistema de reservas
- [ ] Criar histórico de empréstimos
- [ ] Detectar livros atrasados automaticamente
- [ ] Criar multas ou regras de atraso
- [ ] Criar notificações de devolução
- [ ] Implementar configurações reais de conta
- [ ] Criar diferentes níveis de acesso
- [ ] Adicionar dashboard com indicadores

---

## 💡 Possível arquitetura futura

Uma evolução do projeto poderia seguir esta arquitetura:

```text
VITALIS
│
├── Front-end
│   ├── Catálogo
│   ├── Perfil
│   ├── Empréstimos
│   └── Administração
│
├── API
│   ├── Usuários
│   ├── Livros
│   ├── Empréstimos
│   └── Reservas
│
└── Banco de Dados
    ├── users
    ├── books
    ├── loans
    └── reservations
```

Com isso, o projeto poderia evoluir de uma demonstração front-end para um **sistema completo de gerenciamento de biblioteca**.

---

## 🎯 Objetivo do projeto

O VITALIS foi desenvolvido para aplicar conceitos de desenvolvimento web em uma situação prática.

O projeto demonstra conhecimentos em:

- desenvolvimento front-end
- lógica de programação
- gerenciamento de estado
- manipulação do DOM
- design responsivo
- interação com o usuário
- organização de dados
- criação de interfaces modernas

Além de funcionar como projeto acadêmico, ele também pode ser utilizado como parte de um **portfólio de Desenvolvimento Full Stack / Engenharia de Software**.

---

## 👨🏽‍💻 Autor

Desenvolvido por **João Pedro Paranhos**.

[![GitHub](https://img.shields.io/badge/GitHub-J040P-181717?style=for-the-badge&logo=github)](https://github.com/J040P)

---

## ⭐ Sobre o projeto

Se você gostou do VITALIS, deixe uma **⭐ no repositório**.

Isso ajuda a acompanhar a evolução do projeto e fortalece meu portfólio como desenvolvedor.

---

<p align="center">
  <strong>VITALIS</strong><br>
  Modern Library Management Experience
</p>
