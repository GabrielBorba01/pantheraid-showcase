<div align="center">
<img width="180" height="180" alt="apple-touch-icon" src="https://github.com/user-attachments/assets/c3d571c0-58fe-412a-be16-69916d5f8022"/>


# PantheraID

</div>

Sistema web de controle de acesso para shoppings: crachá digital com foto, aprovação em duas etapas e validação por QR code na portaria. Inclui também a gestão de ordens de serviço de prestadores.

> Em desenvolvimento. Os dados exibidos são fictícios.

<div align="center">

https://github.com/user-attachments/assets/c88f7f9c-c60d-4e22-868a-29843e2c5174

</div>


*Fluxo completo: solicitação, aprovação, crachá digital e validação na portaria.*

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
> Todos os dados presentes nas capturas de tela a seguir são fictícios. Todas as imagens presentes também são geradas por inteligência artificial e não representam fotos de pessoas reais.
> Algumas telas podem ter pequenos ajustes visuais.

### Tela de crachá do colaborador
<img width="300" alt="Meu Cracha" src="https://github.com/user-attachments/assets/99997d2b-ec22-4aff-b414-4f255b003ac0" />


### Tela de solicitação de crachá
<img width="300" alt="Solicitação de crachá" src="https://github.com/user-attachments/assets/1c686c2d-8c37-406f-b2dc-868c67f7789b" />


### Tela de aprovação de crachás por gerentes e supervisor de segurança
<img width="300" alt="Aprovação de crachá" src="https://github.com/user-attachments/assets/f14c0ed1-563e-4cb8-92f0-a6ceff1719b6" />


### Tela de crachá válido
<img width="300" alt="Crachá válido" src="https://github.com/user-attachments/assets/bdf56824-8b4b-48e0-aa2d-1a02cffdedca" />

### Tela de gerenciamento dos crachás
> Para gerentes, aparecem somente os crachás da sua loja. Para o supervisor de segurança aparecem todos.
<img width="300" alt="Gerenciamento de crachás" src="https://github.com/user-attachments/assets/b25eda8f-c3ff-42fd-a076-81b3edcc45bb" />

### Tela de solicitação de ordem de serviço
<img width="300" alt="Solicitação de ordem de serviço" src="https://github.com/user-attachments/assets/ad5d3313-da35-4277-844d-50bd634ab907" />

### Tela de gerenciamento de OS
<img width="300" alt="Gerenciamento de ordens de serviço" src="https://github.com/user-attachments/assets/14fc8b80-b141-4a56-a704-6cc4931c675a" />


## Stack

- **Front-end:** React, TypeScript, Vite e PWA
- **Back-end:** Node.js e Express
- **Banco de dados e armazenamento:** PostgreSQL via Supabase
- **Integrações:** Google Cloud Vision (OCR) e Resend (e-mails)

## Segurança

Autenticação com sessão em cookie protegido, controle de acesso por perfil e setor, validação de dados no servidor e limites de requisições em rotas sensíveis. A revisão de segurança continua durante o desenvolvimento.

## Status e próximos passos

Em desenvolvimento. Próximas etapas: testes de leitura do QR code em celulares reais, consulta de lojas na portaria e evolução das integrações.

## Código-fonte

O código da aplicação está em um repositório privado. Este repositório documenta o desenvolvimento e apresenta as funcionalidades.
