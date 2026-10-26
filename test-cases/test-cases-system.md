# Casos de Teste de Sistema - Tela de Login

## CTS-001 - Login com Credenciais Válidas

### Objetivo
Validar que um usuário ativo consiga acessar o sistema utilizando credenciais válidas.

### Requisito Relacionado
RF01, RF02, RF03

### Categoria do Teste
Funcional

### Pré-condições
- Usuário cadastrado e ativo.
- Aplicação disponível.

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

### Resultado Esperado
- Login realizado com sucesso.
- Dashboard exibido.
- Nome do usuário exibido na aplicação.
- Sessão criada.

### Criticidade
Alta

---

## CTS-002 - Login com Senha Inválida

### Objetivo
Validar a exibição de mensagens adequadas para credenciais incorretas.

### Requisito Relacionado
RF02

### Categoria do Teste
Funcional

### Pré-condições
Usuário cadastrado.

### Dados de Teste

| Campo | Valor |
|---------|---------|
| E-mail | usuario@email.com |
| Senha | SenhaErrada |

### Passos
1. Preencher usuário válido.
2. Informar senha incorreta.
3. Clicar em Entrar.

### Resultado Esperado
- Login não realizado.
- Mensagem de erro exibida.
- Usuário permanece na tela de login.

### Criticidade
Alta

---

## CTS-003 - Usuário Inexistente

### Objetivo
Validar comportamento do sistema para usuários não cadastrados.

### Categoria do Teste
Funcional

### Passos
1. Informar credenciais inexistentes.
2. Clicar em Entrar.

### Resultado Esperado
- Acesso negado.
- Mensagem apropriada exibida.

### Criticidade
Alta

---

## CTS-004 - Campo E-mail Obrigatório

### Objetivo
Validar obrigatoriedade do campo e-mail.

### Requisito Relacionado
RN03

### Categoria do Teste
Usabilidade

### Passos
1. Deixar o campo e-mail vazio.
2. Informar senha.
3. Acionar login.

### Resultado Esperado
- Mensagem de validação exibida.
- Login não executado.

### Criticidade
Alta

---

## CTS-005 - Campo Senha Obrigatório

### Objetivo
Validar obrigatoriedade do campo senha.

### Requisito Relacionado
RN03

### Categoria do Teste
Usabilidade

### Passos
1. Informar usuário válido.
2. Deixar senha vazia.
3. Acionar login.

### Resultado Esperado
- Sistema impede autenticação.
- Mensagem de campo obrigatório exibida.

### Criticidade
Alta

---

## CTS-006 - Formato de E-mail Inválido

### Objetivo
Validar consistência da entrada de dados.

### Categoria do Teste
Usabilidade

### Dados de Teste

| Campo | Valor |
|---------|---------|
| E-mail | usuario.com |
| Senha | Senha@123 |

### Passos
1. Informar e-mail com formato inválido.
2. Preencher senha.
3. Tentar login.

### Resultado Esperado
- Sistema exibe erro de validação.
- Login não realizado.

### Criticidade
Média

---

## CTS-007 - Usuário Bloqueado

### Objetivo
Validar a regra de bloqueio de conta.

### Requisito Relacionado
RN01

### Categoria do Teste
Regras de Negócio

### Pré-condições
Usuário bloqueado na base.

### Passos
1. Informar credenciais válidas.
2. Tentar realizar login.

### Resultado Esperado
- Sistema impede acesso.
- Mensagem de conta bloqueada exibida.

### Criticidade
Alta

---

## CTS-008 - Bloqueio Após Cinco Tentativas Inválidas

### Objetivo
Validar bloqueio automático após excesso de tentativas.

### Requisito Relacionado
RN02

### Categoria do Teste
Regras de Negócio

### Passos
1. Informar senha incorreta cinco vezes.
2. Tentar autenticar novamente.

### Resultado Esperado
- Conta bloqueada.
- Login posterior negado.

### Criticidade
Alta

---

## CTS-009 - Login Após Conta Bloqueada

### Objetivo
Validar persistência do bloqueio da conta.

### Categoria do Teste
Regras de Negócio

### Pré-condições
Conta previamente bloqueada.

### Passos
1. Informar usuário e senha corretos.

### Resultado Esperado
- Sistema mantém bloqueio.
- Acesso negado.

### Criticidade
Alta

---

## CTS-010 - Logout do Sistema

### Objetivo
Validar encerramento da sessão.

### Requisito Relacionado
RF08

### Categoria do Teste
Sessão

### Pré-condições
Usuário autenticado.

### Passos
1. Efetuar login.
2. Selecionar opção Logout.

### Resultado Esperado
- Sessão encerrada.
- Usuário redirecionado para tela de login.

### Criticidade
Alta

---

## CTS-011 - Atualização da Página Após Login

### Objetivo
Validar persistência da sessão.

### Categoria do Teste
Sessão

### Pré-condições
Usuário autenticado.

### Passos
1. Realizar login.
2. Atualizar a página utilizando F5.

### Resultado Esperado
- Usuário permanece autenticado.
- Aplicação continua acessível.

### Criticidade
Média

---

## CTS-012 - Encerramento por Inatividade

### Objetivo
Validar expiração automática da sessão.

### Requisito Relacionado
RN05

### Categoria do Teste
Sessão

### Passos
1. Realizar login.
2. Permanecer inativo até o período de expiração.

### Resultado Esperado
- Sessão encerrada automaticamente.
- Novo login solicitado.

### Criticidade
Alta

---

## CTS-013 - Acesso Direto a Página Protegida sem Login

### Objetivo
Validar proteção das áreas restritas.

### Categoria do Teste
Segurança

### Passos
1. Copiar URL de página protegida.
2. Abrir URL sem estar autenticado.

### Resultado Esperado
- Redirecionamento para login.
- Conteúdo protegido não exibido.

### Criticidade
Alta

---

## CTS-014 - Acesso com Token Expirado

### Objetivo
Validar controle de sessão.

### Categoria do Teste
Segurança

### Passos
1. Simular token expirado.
2. Tentar acessar área protegida.

### Resultado Esperado
- Sessão invalidada.
- Solicitação de novo login.

### Criticidade
Alta

---

## CTS-015 - Utilização do Botão Voltar Após Logout

### Objetivo
Validar segurança da navegação.

### Categoria do Teste
Segurança

### Passos
1. Efetuar login.
2. Fazer logout.
3. Utilizar botão Voltar do navegador.

### Resultado Esperado
- Área protegida não deve ser exibida.
- Sistema deve exigir autenticação.

### Criticidade
Alta

---

## CTS-016 - Tentativa de Alteração Manual da URL

### Objetivo
Validar restrições de acesso.

### Categoria do Teste
Segurança

### Passos
1. Estar desconectado.
2. Digitar manualmente uma rota protegida.

### Resultado Esperado
- Usuário redirecionado para login.

### Criticidade
Alta

---

## CTS-017 - Navegação por Teclado

### Objetivo
Validar acessibilidade da tela de login.

### Categoria do Teste
Acessibilidade

### Passos
1. Navegar utilizando apenas TAB.
2. Selecionar Entrar utilizando teclado.

### Resultado Esperado
- Todos os campos recebem foco.
- Navegação funcional sem mouse.

### Criticidade
Média

---

## CTS-018 - Leitura por Tecnologias Assistivas

### Objetivo
Validar acessibilidade para leitores de tela.

### Categoria do Teste
Acessibilidade

### Passos
1. Abrir tela utilizando leitor de tela.
2. Navegar pelos campos.

### Resultado Esperado
- Campos possuem descrição adequada.
- Mensagens podem ser interpretadas pelo leitor.

### Criticidade
Média

---

## CTS-019 - Validação em Resolução Mobile

### Objetivo
Validar responsividade da interface.

### Categoria do Teste
Compatibilidade

### Passos
1. Abrir aplicação em dispositivo móvel.
2. Acessar tela de login.

### Resultado Esperado
- Componentes ajustados à resolução.
- Todos os elementos permanecem utilizáveis.

### Criticidade
Média

---

## CTS-020 - Validação em Diferentes Navegadores

### Objetivo
Validar compatibilidade entre navegadores.

### Categoria do Teste
Compatibilidade

### Passos
1. Executar login utilizando Chrome.
2. Repetir em Edge.
3. Repetir em Firefox.

### Resultado Esperado
- Comportamento consistente em todos os navegadores.

### Criticidade
Média

---

## CTS-021 - Login com Caracteres Especiais

### Objetivo
Validar tratamento de caracteres especiais.

### Categoria do Teste
Casos de Borda

### Dados de Teste

| Campo | Valor |
|---------|---------|
| E-mail | usuario+teste@email.com |
| Senha | Senha@123! |

### Passos
1. Informar credenciais contendo caracteres especiais.
2. Efetuar login.

### Resultado Esperado
- Sistema processa as informações corretamente.

### Criticidade
Média

---

## CTS-022 - Login com Espaços em Branco

### Objetivo
Validar tratamento de espaços antes e após os valores.

### Categoria do Teste
Casos de Borda

### Passos
1. Informar e-mail com espaços extras.
2. Informar senha válida.
3. Efetuar login.

### Resultado Esperado
- Sistema trata adequadamente os espaços.
- Login ocorre conforme regra definida.

### Criticidade
Média

---

## CTS-023 - Campo E-mail com Tamanho Máximo Permitido

### Objetivo
Validar limites definidos para entrada de dados.

### Categoria do Teste
Casos de Borda

### Passos
1. Informar e-mail próximo ao limite permitido.
2. Acionar login.

### Resultado Esperado
- Campo aceita limite suportado.
- Sistema permanece estável.

### Criticidade
Baixa

---

## CTS-024 - Login com Caracteres Unicode

### Objetivo
Validar suporte a caracteres internacionais.

### Categoria do Teste
Casos de Borda

### Dados de Teste

| Campo | Valor |
|---------|---------|
| E-mail | usuário@email.com |
| Senha | Senhaçã123 |

### Passos
1. Informar dados com caracteres Unicode.
2. Tentar login.

### Resultado Esperado
- Sistema trata adequadamente a codificação.
- Não ocorre falha de processamento.

### Criticidade
Baixa

---

## CTS-025 - Tentativas Simultâneas de Login

### Objetivo
Validar comportamento em acessos concorrentes.

### Categoria do Teste
Casos de Borda

### Passos
1. Realizar login simultaneamente em múltiplas abas.
2. Monitorar comportamento da sessão.

### Resultado Esperado
- Sistema segue regra definida para concorrência.
- Não ocorre corrupção da sessão.

### Criticidade
Média