# Casos de Teste de Integração

## CTI-001 - Login com Sucesso

### Pré-condições

Usuário ativo cadastrado.

### Passos

1. Informar usuário válido.
2. Informar senha válida.
3. Clicar em Entrar.

### Resultado Esperado

- Front-end envia requisição.
- API consulta banco.
- Banco retorna dados do usuário.
- API retorna HTTP 200.
- Token é gerado.
- Usuário é redirecionado para Home.

---

## CTI-002 - Senha Inválida

### Pré-condições

Usuário existente.

### Passos

1. Informar usuário válido.
2. Informar senha incorreta.
3. Clicar em Entrar.

### Resultado Esperado

- API consulta banco.
- Validação falha.
- API retorna HTTP 401.
- Mensagem de erro exibida.

---

## CTI-003 - Campos Obrigatórios

### Passos

1. Deixar usuário vazio.
2. Informar senha.
3. Acionar login.

### Resultado Esperado

- Nenhuma requisição enviada para API.
- Mensagem de validação exibida.

---

## CTI-004 - Usuário Bloqueado

### Pré-condições

Usuário marcado como bloqueado na base.

### Passos

1. Informar credenciais válidas.
2. Acionar login.

### Resultado Esperado

- API identifica bloqueio.
- HTTP 403 retornado.
- Acesso negado.