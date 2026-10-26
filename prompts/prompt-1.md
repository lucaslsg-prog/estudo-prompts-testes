# Prompt 01 - Geração de Casos de Teste de Integração

Você é um Especialista em Testes de Integração com experiência em API REST, autenticação e qualidade de software.

Analise os requisitos fornecidos e gere casos de teste de integração considerando a comunicação entre:

- Front-end
- API de Autenticação
- Banco de Dados

Objetivo:

Validar o comportamento da integração entre os componentes, garantindo que dados, regras de negócio e respostas sejam processados corretamente em diferentes condições.

## Cobertura Obrigatória

Gere casos de teste contemplando:

### Fluxos Positivos

- Login realizado com sucesso
- Geração de token
- Recuperação de dados do usuário
- Criação da sessão

### Fluxos Negativos

- Usuário inexistente
- Senha inválida
- Campos obrigatórios não preenchidos
- Formatos inválidos
- Usuário bloqueado
- Usuário inativo

### Integração e Persistência

- Consulta ao banco de dados
- Atualização de contador de tentativas
- Bloqueio de conta após limite de tentativas
- Recuperação dos dados do usuário

### Segurança

- Token inválido
- Token expirado
- Acesso não autorizado
- Tentativa de reutilização de token

### Tratamento de Erros

- Banco de dados indisponível
- Timeout na API
- Falha de comunicação entre componentes
- Exceções inesperadas

## Status HTTP que DEVEM ser cobertos quando aplicável

- 200 OK
- 201 Created
- 204 No Content
- 400 Bad Request
- 401 Unauthorized
- 403 Forbidden
- 404 Not Found
- 408 Request Timeout
- 409 Conflict
- 422 Unprocessable Entity
- 429 Too Many Requests
- 500 Internal Server Error
- 502 Bad Gateway
- 503 Service Unavailable

## Para cada caso de teste informe

- ID
- Título
- Objetivo
- Requisito relacionado
- Componentes envolvidos
- Pré-condições
- Dados de teste
- Passos
- Status HTTP esperado
- Resultado esperado
- Criticidade (Alta, Média ou Baixa)

## Requisitos

[Cole aqui os requisitos funcionais e regras de negócio]