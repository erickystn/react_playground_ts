# ⚛️ React + TypeScript Playground — Laboratório de Fundamentos

![React](https://img.shields.io/badge/React-18.2-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-5.2-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-5.0-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![ESLint](https://img.shields.io/badge/ESLint-8.5-4B32C3?style=for-the-badge&logo=eslint&logoColor=white)
![Status](https://img.shields.io/badge/Status-Concluído-brightgreen?style=for-the-badge)
![Licença](https://img.shields.io/badge/Licença-MIT-yellow?style=for-the-badge)

---

## 🔗 Acesso e Ambiente da Aplicação

* **Ambiente de Desenvolvimento:** `http://localhost:5173`
* **Servidor Local:** Desenvolvido com **Vite** com Hot Module Replacement (HMR)

---

## 📖 Visão Geral

O **react_playground_ts** é um ambiente laboratório estruturado para o estudo, prática e fixação dos conceitos fundamentais do **React** utilizando **TypeScript** e **Vite**, desenvolvido durante o bootcamp **Generation Brasil (Turma JS13)**.

O repositório foi construído de forma modular para isolar e exercitar os blocos construtivos essenciais de aplicações front-end modernas: componentização atômica, fluxo unidirecional de dados com **Props tipadas**, gerenciamento de estado reativo com **`useState`**, controle de ciclo de vida e efeitos colaterais com **`useEffect`**, e lógica de **renderização condicional**.

---

## ✨ Módulos e Laboratórios Práticos

O laboratório divide-se em 4 páginas e componentes conceituais em `src/pages/`:

### 1. 🔢 Laboratório Contador (`src/pages/contador/Contador.tsx`)
* **Conceito Trabalhado:** Gerenciamento de Estado Reativo com `useState`.
* **Mecânica:** Implementa um contador incremental simples onde o clique no botão atualiza o estado interno e re-renderiza o valor atual na interface instantaneamente.

### 2. 📬 Laboratório Home com Props (`src/pages/home/Home.tsx`)
* **Conceito Trabalhado:** Comunicação entre Componentes e Tipagem Estrita de Props.
* **Mecânica:** Exemplo de componente puro que recebe e consome propriedades externas através de uma interface TypeScript (`homeProps { titulo: string; texto: string; }`), demonstrando previsibilidade e desacoplamento.

### 3. 🔀 Laboratório Login com Renderização Condicional (`src/pages/login/Login.tsx`)
* **Conceito Trabalhado:** Renderização Condicional com Operadores Ternários.
* **Mecânica:** Alterna dinamicamente a visão entre a tela de boas-vindas do componente `Home` (quando autenticado) e a interface de formulário de login (quando deslogado), dependendo do estado booleano `isLogged`.

### 4. ⏳ Laboratório Tarefa com Efeitos Colaterais (`src/pages/tarefa/Tarefa.tsx`)
* **Conceito Trabalhado:** Ciclo de Vida e Hook `useEffect` com Array de Dependências.
* **Mecânica:** Dispara uma reação assíncrona orientada a mudanças de estado — ao marcar a tarefa como concluída (`setCompleted(true)`), o efeito colateral é executado, atualizando a mensagem comemorativa de conclusão na tela.

---

## 🎯 Diferenciais e Destaques Técnicos

1. **Tipagem Estrita com Interfaces TypeScript:** Todas as propriedades e estados são explicitamente tipados, eliminando ambiguidades e prevenindo erros de runtime comuns em JavaScript puro.
2. **Ambiente Leve e Rápido com Vite 5:** Inicialização instantânea e atualização de módulos em milissegundos via Hot Module Replacement.
3. **Isolamento Didático:** Arquitetura limpa permitindo testar e renderizar cada componente individualmente no `App.tsx` sem dependências cruzadas complexas.
4. **Estilização Padronizada em CSS Puro:** Layout limpo com tipografia moderna (fonte Poppins), botões estilizados com cantos arredondados e paleta de cores consistente em tons de azul e cinza claro.

---

## 🏗️ Estrutura do Repositório

```text
react_playground_ts/
├── public/                     # Recursos públicos estáticos (ex: favicon)
├── src/
│   ├── assets/                 # SVGs e imagens do React
│   ├── pages/                  # Módulos didáticos de experimentação
│   │   ├── contador/           # Prática com useState (contador numérico)
│   │   │   └── Contador.tsx
│   │   ├── home/               # Prática com interfaces e Props
│   │   │   └── Home.tsx
│   │   ├── login/              # Prática com renderização condicional
│   │   │   └── Login.tsx
│   │   └── tarefa/             # Prática com useEffect e dependências
│   │       └── Tarefa.tsx
│   ├── App.css                 # Estilos utilitários, tipografia e botões
│   ├── App.tsx                 # Componente raiz que orquestra a exibição dos módulos
│   ├── index.css               # Reset de estilos globais
│   ├── main.tsx                # Ponto de entrada do DOM React (StrictMode)
│   └── vite-env.d.ts           # Declaração de tipos de ambiente do Vite
├── .eslintrc.cjs               # Regras e plugins de linting do ESLint
├── package.json                # Dependências (React 18, Vite, TypeScript)
├── tsconfig.json               # Configurações do compilador TypeScript
└── vite.config.ts              # Configurações do plugin oficial do React
```

---

## ⚙️ Requisitos e Instalação

### Pré-requisitos
* **Node.js:** Versão 18 ou superior.
* **Gerenciador de Pacotes:** `npm` ou `yarn`.

### 1. Clonar o Repositório
```bash
git clone https://github.com/erickystn/react_playground_ts.git
cd react_playground_ts
```

### 2. Instalar as Dependências
Com npm:
```bash
npm install
```
Ou com yarn:
```bash
yarn install
```

---

## 🚀 Como Executar

### Ambiente de Desenvolvimento
```bash
npm run dev
# ou
yarn dev
```
Abra o navegador no endereço `http://localhost:5173`.

### Compilação e Checagem de Tipos
```bash
npm run build
```

### Pré-visualização do Build de Produção
```bash
npm run preview
```

---

## 💻 Exemplos de Código dos Laboratórios

### 1. Estado Reativo com `useState`
```tsx
import { useState } from "react";

function Contador() {
  const [valor, setValor] = useState(0);

  return (
    <div>
      <h2>Componente Contador</h2>
      <p>O valor atual é: {valor}</p>
      <button onClick={() => setValor(valor + 1)}>Adicionar 1</button>
    </div>
  );
}
```

### 2. Efeitos Colaterais com `useEffect`
```tsx
import { useState, useEffect } from "react";

function Tarefa() {
  const [completed, setCompleted] = useState(false);
  const [mensagem, setMensagem] = useState("");

  useEffect(() => {
    if (completed) {
      setMensagem("Parabéns! Você concluiu a tarefa!");
    }
  }, [completed]); // Disparado somente quando `completed` for alterado

  return (
    <div>
      <h3>{mensagem}</h3>
      <button onClick={() => setCompleted(true)}>Concluir Tarefa</button>
    </div>
  );
}
```

---

## 🛠️ Tecnologias Utilizadas

| Tecnologia | Versão | Finalidade |
| :--- | :--- | :--- |
| **React** | 18.2 | Biblioteca para construção de interfaces web declarativas |
| **TypeScript** | 5.2 | Tipagem estática, interfaces e detecção precoce de bugs |
| **Vite** | 5.0 | Servidor de desenvolvimento rápido e bundler de produção |
| **ESLint** | 8.55 | Linter de padronização de boas práticas e hooks do React |

---

## 📈 Próximos Passos de Estudo (Roadmap)

Os conceitos praticados neste playground serviram como base para os projetos completos da formação:
- [x] Fundamentos de estado (`useState`) e efeitos (`useEffect`).
- [x] Tipagem de componentes e propriedades com TypeScript.
- [ ] Roteamento de páginas com **React Router DOM** (aplicado no `generation_JS13_blogpessoal_React`).
- [ ] Gerenciamento de estado global com **Context API** (`AuthContext`).
- [ ] Integração com APIs RESTful via **Axios**.
- [ ] Estilização utilitária avançada com **Tailwind CSS**.

---

## 👤 Autor & 📄 Licença

Desenvolvido por **[Ericky Sant'ana](https://github.com/erickystn)** durante a trilha de desenvolvimento front-end da **Generation Brasil**.

Distribuído sob a licença **MIT**.
