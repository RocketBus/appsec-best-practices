### Code Review com foco em Segurança

Este documento serve como guia prático para revisar códigos com foco em segurança de aplicações.  
A ideia não é só encontrar bug, é evitar que risco chegue em produção.


#### O que revisar em primeiro lugar

Durante um code review, priorize:

- Pontos de entrada do usuário (input)
- Autenticação e autorização
- Manipulação de dados sensíveis
- Integração com serviços externos
- Configuração de segurança (headers, tokens, segredos, etc.)


#### Checklist de Segurança para Code Review

#### 1. Entrada de dados (Input)

- Toda entrada do usuário é validada no backend?
- Existe risco de SQL Injection, Command Injection ou XSS?
- Os dados são sanitizados conforme o contexto (HTML, SQL, Shell, etc)?
- Evite confiar em validações feitas só no frontend.


#### 2. Autenticação e Sessão

- Tokens são gerados de forma segura?
- O tempo de expiração está adequado?
- MFA é respeitado onde deveria?
- Dados de sessão estão sendo expostos?



#### 3. Autorização

- O controle de acesso é feito no backend ou só na UI?
- Existe validação de permissões em todas as rotas sensíveis?
- Não há bypass por manipulação de parâmetros?



#### 4. Dados sensíveis

- Dados sensíveis estão criptografados em repouso?
- Existe vazamento em logs ou respostas da API?
- Tokens, senhas ou chaves estão hardcoded?


#### 5. Integrações Externas

- APIs externas são chamadas de forma segura (HTTPS, validação de certificados)?
- Existe validação de respostas?
- Existe timeout e retry controlado?


#### 6. Erros e exceções

- O sistema retorna mensagens genéricas para o usuário?
- Logs não expõem stacktrace em produção?
- Erros são tratados ou só ignorados?


#### 7. Dependências

- As libs estão atualizadas?
- Passam em SCA?
- Não há dependências abandonadas ou vulneráveis?


#### 8. Configurações de Segurança

- Headers de segurança configurados? (CSP, HSTS, etc)
- CORS está restrito corretamente?
- Secrets não estão em variáveis expostas no frontend?
