### Dynamic Application Security Testing (DAST)

Este documento apresenta o conceito de Testes Dinâmicos de Segurança (DAST),
com foco em aplicações web e APIs em execução.

O objetivo é identificar vulnerabilidades exploráveis em runtime,
simulando o comportamento real de um atacante.

---

## O que é DAST

DAST (Dynamic Application Security Testing) é uma abordagem de teste
que analisa a aplicação enquanto ela está rodando, enviando requisições
maliciosas e observando as respostas.

Diferente de SAST (estático), o DAST não analisa código-fonte.
Ele testa a aplicação como um usuário (ou atacante) externo.

---

## O que o DAST detecta na prática

DAST é eficaz para identificar falhas como:

- SQL Injection
- Cross-Site Scripting (XSS)
- Falhas de autenticação e autorização
- Configurações inseguras em headers
- Exposição de endpoints e rotas não protegidas
- Injeções em APIs REST e GraphQL
- Upload inseguro de arquivos
- Redirecionamentos inseguros

---

## Onde aplicar DAST

DAST deve ser executado em ambientes dedicados, nunca em produção:

- Ambientes de homologação (staging)
- Ambientes de teste
- Ambientes controlados de desenvolvimento

Aplicar DAST em produção pode causar indisponibilidade.

---

## Abordagem Prática

DAST pode ser feito de forma:

### Manual
- Testes exploratórios via navegador
- Uso de proxy como Burp Suite ou OWASP ZAP
- Manipulação direta de requisições

### Automatizada
- Scanners como OWASP ZAP, Nikto, Burp Scanner
- Pipes automatizados em CI/CD
- Agendamento de scans periódicos

---

## Ferramentas Comuns

- OWASP ZAP
- Burp Suite
- Nikto
---

## Boas Práticas para DAST

- Nunca rodar DAST contra sistemas produtivos.
- Utilizar contas com diferentes níveis de acesso.
- Validar falsos positivos antes de abrir ticket.
- Reexecutar após correções.
- Registrar evidências (request + response).
