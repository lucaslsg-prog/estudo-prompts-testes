# Casos de Teste de Integração - Tela de Login

## CTI-001 - Login com Credenciais Válidas

### Objetivo
Validar a autenticação bem-sucedida de um usuário ativo.

### Requisito Relacionado
RF01, RF02, RF03

### Componentes Envolvidos
- Front-end
- API de Autenticação
- Banco de Dados

### Pré-condições
- Usuário cadastrado e ativo.
- Senha válida.

### Dados de Teste
| Campo | Valor |
|---------|---------|
| E-mail | usuario@email.com |
| Senha | Senha@123 |

### Passos
1. Acessar a tela de login.
2. Informar e-mail válido.
3. Informar senha válida.
4. Clicar em Entrar.

### Status HTTP Esperado
`200 OK`

### Resultado Esperado
- Front-end envia a requisição para a API.
- API consulta o banco de dados.
- Credenciais são validadas.
- Token JWT é gerado.
- Dados do usuário são retornados.
- Sessão é criada.

### Criticidade
Alta

---

## CTI-002 - Login com Senha Inválida

### Objetivo
Validar a rejeição do login quando a senha estiver incorreta.

### Requisito Relacionado
RF02

### Componentes Envolvidos
- Front-end
- API
- Banco de Dados

### Pré-condições
- Usuário existente.

### Dados de Teste
| Campo | Valor |
|---------|---------|
| E-mail | usuario@email.com |
| Senha | senhaErrada |

### Passos
1. Informar usuário válido.
2. Informar senha incorreta.
3. Clicar em Entrar.

### Status HTTP Esperado
`401 Unauthorized`

### Resultado Esperado
- Usuário não autentic