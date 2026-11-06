# Cadastro de Usuários

Aplicação front-end desenvolvida em React para cadastrar, visualizar e excluir usuários. O projeto consome uma API REST local e possui duas páginas: um formulário de cadastro e uma listagem dos usuários registrados.

## Funcionalidades

- Cadastro de usuários com nome, idade e e-mail
- Listagem dos usuários cadastrados
- Exclusão de usuários
- Navegação entre cadastro e listagem
- Geração de avatar para cada usuário

## Tecnologias

- [React](https://react.dev/)
- [Vite](https://vite.dev/)
- [React Router](https://reactrouter.com/)
- [Axios](https://axios-http.com/)
- [Styled Components](https://styled-components.com/)
- [ESLint](https://eslint.org/)

## Pré-requisitos

Antes de começar, tenha instalado:

- [Node.js](https://nodejs.org/) em uma versão compatível com o Vite 8
- npm ou Yarn
- Uma API REST executando em `http://localhost:3000`

## Instalação

Clone o repositório, acesse a pasta do projeto e instale as dependências:

```bash
npm install
```

Inicie o servidor de desenvolvimento:

```bash
npm run dev
```

Abra no navegador o endereço exibido pelo Vite, normalmente `http://localhost:5173`.

> Se preferir Yarn, use `yarn` e `yarn dev`.

## API necessária

O endereço base da API está configurado em `src/services/api.js` como `http://localhost:3000`. Ela deve disponibilizar os seguintes endpoints:

| Método | Rota | Descrição |
| --- | --- | --- |
| `POST` | `/usuarios` | Cadastra um usuário |
| `GET` | `/usuarios` | Retorna todos os usuários |
| `DELETE` | `/usuarios/:id` | Exclui um usuário pelo ID |

Exemplo do corpo enviado no cadastro:

```json
{
  "name": "Maria Silva",
  "age": 25,
  "email": "maria@email.com"
}
```

A listagem espera receber um array com objetos neste formato:

```json
[
  {
    "id": 1,
    "name": "Maria Silva",
    "age": 25,
    "email": "maria@email.com"
  }
]
```

Caso a API utilize outro endereço, altere a propriedade `baseURL` em `src/services/api.js`.

## Rotas da aplicação

| Rota | Página |
| --- | --- |
| `/` | Formulário de cadastro |
| `/lista-de-usuarios` | Lista de usuários |

## Scripts disponíveis

```bash
npm run dev      # inicia o ambiente de desenvolvimento
npm run build    # gera a versão de produção em dist/
npm run preview  # executa localmente a versão de produção
npm run lint     # verifica o código com ESLint
```

## Estrutura do projeto

```text
src/
├── assets/              # imagens e ícones
├── components/          # componentes reutilizáveis
├── pages/
│   ├── Home/            # formulário de cadastro
│   └── ListaUsuarios/   # listagem e exclusão
├── services/
│   └── api.js           # configuração do Axios
├── styles/              # estilos globais
├── main.jsx             # ponto de entrada
└── routes.jsx           # definição das rotas
```

## Build de produção

Para gerar os arquivos otimizados da aplicação:

```bash
npm run build
```

O resultado será salvo na pasta `dist/`.
