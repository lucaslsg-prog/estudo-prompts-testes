# Casos de Teste de Sistema

## CTS-001 - Login com Credenciais Válidas

### Objetivo

Validar acesso ao sistema utilizando credenciais válidas.

### Pré-condições

Usuário ativo cadastrado.

### Passos

1. Acessar a tela de login.
2. Informar e-mail válido.
3. Informar senha válida.
4. Clicar em Entrar.

### Resultado Esperado

- Login realizado com sucesso.
- Usuário direcionado para a página inicial.
- Dados do usuário carregados.
- Sessão criada.

---

## CTS-002 - Login com Senha Inválida

### Objetivo

Validar tratamento de erro para credenciais inválidas.

### Pré-condições

Usuário cadastrado.

### Passos

1. Informar e-mail válido.
2. Informar senha inválida.
3. Clicar em Entrar.

### Resultado Esperado

- Login não realizado.
- Mensagem de usuário ou senha inválidos exibida.
- Usuário permanece na tela de login.

---

## CTS-003 - Bloqueio após Tentativas Inválidas

### Objetivo

Validar regra de bloqueio de conta.

### Pré-condições

Usuário ativo.

### Passos

1. Realizar cinco tentativas consecutivas com senha incorreta.
2. Informar credenciais corretas.
3. Tentar efetuar login.

### Resultado Esperado

- Conta bloqueada.
- Acesso negado.
- Mensagem de bloqueio exibida.

---

## CTS-004 - Logout do Sistema

### Objetivo

Validar encerramento de sessão.

### Pré-condições

Usuário autenticado.

### Passos

1. Realizar login.
2. Acessar menu da conta.
3. Selecionar Logout.

### Resultado Esperado

- Sessão encerrada.
- Token removido.
- Usuário redirecionado para tela de login.

---

## CTS-005 - Acesso Direto a Área Protegida sem Login

### Objetivo

Validar controle de acesso.

### Pré-condições

Usuário não autenticado.

### Passos

1. Abrir URL de uma página protegida.

### Resultado Esperado

- Acesso negado.
- Redirecionamento para tela de login.
- Nenhuma informação protegida exibida.