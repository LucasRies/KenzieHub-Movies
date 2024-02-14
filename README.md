### 1. Páginas e componentes
Crie a estrutura básica de componentes do projeto, incluindo as três páginas: Login, Register e Dashboard. Componentizar formulários e demais estruturas seria uma excelente divisão de arquitetura para o seu projeto.

### 2. Rotas da aplicação
Implemente as rotas da aplicação utilizando o React Router Dom. Sugestões de rotas:

- `/` para o componente LoginPage
- `/register` para o componente RegisterPage
- `/dashboard` para o componente DashboardPage

Crie redirecionamentos entre a rota principal e a rota de registro por meio do botão "Cadastre-se", bem como o redirecionamento do botão "Voltar" para a página inicial, na tela de registro.

### 3. Formulários
Utilize o React Hook Form para gerenciar os formulários e estabeleça as seguintes validações:

**Formulário de Registro:**
- `name`: obrigatório
- `email`: obrigatório e deve ser um email válido
- `password`: obrigatório, com pelo menos 8 caracteres, uma letra maiúscula, uma letra minúscula e um número
- `confirmPassword`: obrigatório e deve corresponder ao valor fornecido em `password`
- `bio`: obrigatório
- `contact`: obrigatório
- `course_module`: obrigatório

**Formulário de Contato:**
- `email`: obrigatório
- `password`: obrigatório

### 4. Funcionalidades de Login, Logout e Cadastro
Com os formulários configurados, crie as funcionalidades de:

**Registro:**
- Realize o registro por meio da rota `POST /users` (confira as especificações na documentação).
- Em caso de sucesso, redirecione o usuário para a página inicial.

**Login:**
- Realize o login por meio da rota `POST /sessions` (confira as especificações na documentação).
- Armazene o usuário fornecido na resposta da requisição em um estado (preferencialmente em um componente alto na aplicação).
- Armazene a token no localStorage.
- Redirecione o usuário para `/dashboard` após o processo.

**Logout:**
- Limpe o estado de usuário.
- Remova a token do localStorage.
- Redirecione o usuário para a página inicial.

-----------------------------------------------------------------------

### 1 e 2. Refatoração em contexto
Crie um contexto para centralizar todas as rotinas de usuário. Mova para o contexto os estados e funcionalidades:

- Estado de usuário
- Função de cadastro
- Função de login
- Função de logout

Não esqueça de compartilhar tudo no `value` do provider.

### 3 e 4. Autologin
Com a refatoração bem sucedida, crie uma função de autologin dentro do contexto de usuário. Utilize `useEffect` para realizar uma requisição de `GET` para `/profile` e, assim, garantir que o usuário não seja deslogado ao atualizar a página. Proteja suas rotas utilizando os conceitos de React Router Dom (`Outlet` / `Navigate`).
