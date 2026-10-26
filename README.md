# Uso de IA Generativa para Apoio a Testes de Integração e de Sistema

## Objetivo

Este projeto apresenta um experimento utilizando Inteligência Artificial Generativa (GenAI) para apoiar a criação de testes de integração e de Sistema.

O cenário escolhido foi um fluxo de autenticação de usuários (Tela de Login), envolvendo a comunicação entre Front-end, API de Autenticação e Banco de Dados.

A atividade tem como objetivo avaliar como diferentes tipos de prompts influenciam a geração de casos de teste de integração e a qualidade dos resultados obtidos.

---

## Cenário de Integração

O sistema possui uma tela de login onde o usuário informa suas credenciais para acessar uma aplicação.

### Componentes Envolvidos

```text
Front-end
    │
    ▼
API de Autenticação
    │
    ▼
Banco de Dados
```

### Fluxo Principal

1. Usuário informa e-mail e senha.
2. Front-end envia requisição para API.
3. API valida credenciais.
4. Banco de dados consulta o cadastro do usuário.
5. API retorna sucesso ou falha.
6. Front-end apresenta o resultado ao usuário.

---

## Requisitos Funcionais

### RF01 - Realizar Login

O sistema deve permitir que usuários autenticados acessem a aplicação.

### RF02 - Validar Credenciais

O sistema deve validar usuário e senha consultando a base de dados.

### RF03 - Retornar Token

Quando as credenciais forem válidas, a API deverá retornar um token JWT.

### RF04 - Retornar Erro

Quando as credenciais forem inválidas, a API deverá retornar uma mensagem de erro.

### RF05 - Manter Sessão

O Front-end deverá armazenar o token de autenticação para utilização nas requisições protegidas.

---

## Regras de Negócio

### RN01

Usuários bloqueados não podem realizar login.

### RN02

Após 5 tentativas inválidas consecutivas a conta deverá ser bloqueada.

### RN03

Usuário e senha são campos obrigatórios.

---

## Tipos de Prompt Utilizados

### Prompt 1 – Geração de Cenários de Integração

Objetivo:

Gerar testes focados na comunicação entre Front-end, API e Banco de Dados.

Arquivo:

```text
prompts/prompt-1.md
```

---

### Prompt 2 – Geração de Casos de Teste de Sistema

Objetivo:

Gerar cenários de teste considerando o comportamento completo da aplicação sob a perspectiva do usuário final.

Arquivo:

```text
prompts/prompt-2.md
```

---

## Resultados Obtidos

Os casos de teste gerados estão disponíveis em:

```text
test-cases/test-cases-integration/
test-cases/test-cases-system/
```

---

## Análise dos Resultados

### Prompt 1 - Testes de Integração

O primeiro prompt gerou casos focados na comunicação entre os componentes da solução, validando a troca de informações entre Front-end, API de autenticação e Banco de Dados. Os cenários cobriram validações de requisições, respostas HTTP, consulta de dados e aplicação das regras de negócio durante a integração.

### Prompt 2 - Testes de Sistema

O segundo prompt gerou cenários orientados ao comportamento do sistema sob a perspectiva do usuário final. Os casos produzidos abordaram jornadas completas como autenticação, bloqueio de conta, controle de sessão, logout e acesso a áreas protegidas.

### Influência dos Prompts

Foi possível observar que prompts mais específicos geram resultados mais aderentes ao objetivo do teste. Enquanto o prompt de integração produziu cenários técnicos focados na comunicação entre componentes, o prompt de sistema gerou cenários funcionais completos voltados à validação da aplicação como um todo.

### Ajustes Realizados

Para melhorar os resultados foi necessário:

- Especificar claramente o tipo de teste desejado.
- Definir os componentes envolvidos.
- Solicitar cenários positivos e negativos.
- Definir um formato padronizado para os casos de teste.
- Informar explicitamente o papel da IA (Especialista em Integração ou Especialista em Testes de Sistema).

Esses ajustes aumentaram a qualidade, a diversidade e o detalhamento dos casos de teste gerados pela LLM.
`

### Ajustes Necessários

Os primeiros resultados foram muito genéricos.

Para melhorar a qualidade das respostas foi necessário:

- Especificar os componentes envolvidos.
- Solicitar explicitamente cenários positivos e negativos.
- Exigir validação de status HTTP.
- Exigir cobertura de erros e indisponibilidade.
- Definir um formato padronizado para os casos de teste.

---

## Conclusão

A experiência demonstrou que a qualidade dos casos de teste gerados pela IA é diretamente influenciada pela qualidade do prompt utilizado.

Prompts mais detalhados produziram cenários mais completos, com maior cobertura funcional e de tratamento de falhas, tornando a IA uma ferramenta útil para apoiar o processo de testes de integração.
`