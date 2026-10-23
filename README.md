# PantheraID

Sistema web de controle de acesso para shoppings: crachá digital com foto, aprovação em duas etapas e validação por QR code na portaria. Inclui também a gestão de ordens de serviço de prestadores.

> Em desenvolvimento. Os dados exibidos são fictícios.

[GIF do fluxo: cadastro → aprovação → crachá com QR code → validação na portaria]

## Problema

Crachás de papel não têm controle de validade nem de revogação. Quem é desligado continua com o crachá, e a portaria não tem como saber. Ordens de serviço circulam por mensagens, sem histórico pesquisável.

## Solução

- **Cadastro com verificação de identidade**, com leitura do documento por OCR e validação automática da foto.
- **Aprovação em duas etapas**, pela gestão da loja e pela chefia de segurança.
- **Crachá digital com validade**, com QR code que expira em 60 segundos.
- **Validação na portaria**, com exibição de foto, nome e situação do crachá.
- **Revogação, expiração automática e log de auditoria** das ações sensíveis.
- **Perfis com permissões** verificadas no servidor a cada requisição.

## Ordens de serviço de prestadores

O gerente da loja abre a ordem de serviço com o formulário de obra, que inclui horários permitidos, EPIs e documentos técnicos, e a lista de trabalhadores. O setor de Operação aprova ou reprova, com motivo registrado e aviso por e-mail. A segurança acompanha as atividades em andamento em uma aba que considera o horário do shopping, inclusive o turno que passa da meia-noite.

## Telas

![Dashboard](https://github.com/user-attachments/assets/36923860-a003-4186-a979-9bf7cc9d37e8)
![Solicitação de crachá](https://github.com/user-attachments/assets/7f52ca51-087d-4909-a9e2-1c535960b1c8)
![Aprovação de solicitações](https://github.com/user-attachments/assets/87b56291-4880-4efa-a836-1d4e6855f51c)
![Validação por QR Code](https://github.com/user-attachments/assets/a25aeea9-2e2e-4681-a55b-59825e9c142c)
![Gerenciamento de crachás](https://github.com/user-attachments/assets/052cb985-507c-4b05-bd51-0f2552a51dc1)

## Stack

- **Front-end:** React, TypeScript, Vite e PWA
- **Back-end:** Node.js e Express
- **Banco de dados e armazenamento:** PostgreSQL via Supabase
- **Integrações:** Google Cloud Vision (OCR), Resend (e-mails) e Mercado Pago (cobrança, opcional)

## Segurança

Autenticação com sessão em cookie protegido, controle de acesso por perfil e setor, validação de dados no servidor e limites de requisições em rotas sensíveis. A revisão de segurança continua durante o desenvolvimento.

## Status e próximos passos

Em desenvolvimento. Próximas etapas: testes de leitura do QR code em celulares reais, consulta de lojas na portaria e evolução das integrações.

## Código-fonte

O código da aplicação está em um repositório privado. Este repositório documenta o desenvolvimento e apresenta as funcionalidades.
