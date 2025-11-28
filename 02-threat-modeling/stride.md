STRIDE – Modelagem de Ameaças

STRIDE é um modelo criado pela Microsoft para ajudar a identificar ameaças de segurança ainda na fase de design de sistemas e aplicações.
Ele organiza os riscos em seis categorias e serve como guia para pensar como um atacante antes do código ir para produção.

Categorias do STRIDE

S – Spoofing (Falsificação de identidade)
Quando alguém se passa por outro usuário ou serviço.
Exemplo: uso de credenciais vazadas para assumir uma conta.

T – Tampering (Adulteração de dados)
Quando dados são alterados indevidamente.
Exemplo: manipulação de parâmetros em uma requisição API.

R – Repudiation (Repúdio)
Quando uma ação não pode ser provada depois.
Exemplo: usuário realiza uma operação crítica, mas não há logs confiáveis.

I – Information Disclosure (Vazamento de informação)
Quando dados sensíveis vazam para quem não deveria ter acesso.
Exemplo: retorno de dados de cartão em resposta da API.

D – Denial of Service (Negação de serviço)
Quando o sistema se torna indisponível por sobrecarga ou abuso.
Exemplo: ataque que esgota recursos do servidor.

E – Elevation of Privilege (Elevação de privilégio)
Quando um usuário ganha acesso acima do que deveria.
Exemplo: usuário comum acessando funções de admin.

Como aplicar STRIDE

Desenhe o fluxo do sistema (usuário → frontend → backend → banco → serviços).

Para cada ponto, aplique o STRIDE:

Pode ser falsificado?

Pode ser alterado?

Pode causar vazamento?

Pode sofrer DoS?

Existe risco de elevação de privilégio?

Liste as ameaças.

Defina controles de segurança para cada uma.

Exemplo prático

Fluxo: Login de usuário

Categoria	Possível ameaça	Controle
Spoofing	Uso de credenciais vazadas	MFA
Tampering	Alteração de token	Assinatura e validação de JWT
Repudiation	Falta de rastreabilidade	Logs com integridade
Info Disclosure	Vazamento de dados	Minimizar retorno
DoS	Brute force	Rate limit
Elevation	Bypass de roles	RBAC e validação server-side
Por que STRIDE importa em AppSec?

• Ajuda a antecipar riscos ainda na fase de arquitetura
• Facilita a conversa com devs e produto
• Apoia decisões técnicas mais seguras
• Reduz custo de correção lá na frente
