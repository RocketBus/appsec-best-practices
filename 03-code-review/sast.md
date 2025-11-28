### SAST – Static Application Security Testing no Code Review

Este documento explica como utilizar SAST (Static Application Security Testing)
como apoio no processo de Code Review, focando em prevenção e não só correção.

O objetivo é integrar análise automática com revisão humana.

---

## O que é SAST

SAST é uma técnica de segurança que analisa o código-fonte sem precisar
executar a aplicação.

Ela busca padrões inseguros, más práticas e vulnerabilidades conhecidas
diretamente no código.

---

## Por que usar SAST junto do Code Review?

SAST não substitui o revisor, mas ajuda a:

- Identificar falhas óbvias antes da revisão manual.
- Direcionar o foco do revisor para riscos reais.
- Reduzir erros humanos em análises repetitivas.
- Padronizar critérios de segurança.

Enquanto o SAST varre, o humano pensa.

---

## Onde o SAST entra no processo

O SAST deve rodar:

1. Durante o desenvolvimento (local).
2. No Pull Request.
3. No pipeline de CI/CD.

idealmente antes do merge.

---

## Como usar SAST no Code Review

Durante a análise de um PR:

- Verifique os resultados do SAST.
- Priorize falhas críticas e altas.
- Confirme se são falsos positivos antes de ignorar.
- Se a ferramenta não apontou nada, não confie cegamente.

SAST é apoio, não oráculo.

---

## Tipos de problemas que o SAST encontra

- Hardcoded secrets
- SQL injection
- Uso inseguro de criptografia
- Falhas de autenticação
- Falta de validações de input
- Uso de funções perigosas
- Falta de tratamento de erros
- Dependências inseguras

---

## Boas práticas ao usar SAST

- Mantenha regras e políticas atualizadas.
- Evite ignorar alertas sem justificativa.
- Documente exceções.
- Integre no CI, não rode só manualmente.
- Priorize qualidade, não só quantidade de alertas.
