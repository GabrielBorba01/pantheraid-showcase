<img width="884" height="1779" alt="image" src="https://github.com/user-attachments/assets/db3b0f65-9f9f-4a37-9fef-bc24335a0e21" /># PantheraID - Showcase

Sistema web para gerenciamento, emissão e validação de crachás corporativos.

Este repositório é uma apresentação pública do **PantheraID**. O código-fonte da aplicação é mantido em um repositório privado.

> O projeto está em desenvolvimento contínuo. Funcionalidades e interface podem sofrer alterações.

---

## Sobre o projeto

O PantheraID surgiu com o objetivo de digitalizar e centralizar o processo de emissão e gerenciamento de crachás dentro de organizações que possuem diferentes lojas, setores e níveis de acesso.

A aplicação permite acompanhar todo o ciclo de vida de um crachá, desde o cadastro e verificação do usuário até a solicitação, aprovação, emissão, validação e eventual renovação ou revogação.

Em vez de depender de processos manuais e informações espalhadas, o sistema concentra os dados em um único ambiente e aplica regras específicas de acordo com o perfil de cada usuário.

---

## Fluxo principal

O funcionamento básico da plataforma segue este fluxo:

```text
Cadastro
   ↓
Verificação de identidade
   ↓
Solicitação de crachá
   ↓
Análise / aprovação
   ↓
Emissão do crachá
   ↓
Validação via QR Code
   ↓
Renovação, expiração ou revogação
```

Dependendo do perfil do usuário, a solicitação pode passar por diferentes etapas de aprovação antes da emissão.

---

## Funcionalidades

Atualmente, o PantheraID conta com funcionalidades como:

* Cadastro e autenticação de usuários
* Recuperação de senha por e-mail
* Verificação de usuário através de documento
* OCR para identificação de informações no documento
* Solicitação de crachá com envio de foto
* Fluxo de aprovação por diferentes níveis de acesso
* Aprovação e rejeição de solicitações
* Registro do motivo de rejeição
* Emissão de crachá digital
* Validade automática dos crachás
* Renovação de crachás
* Revogação de crachás
* Expiração automática
* QR Code para identificação
* Leitura e validação de QR Code
* Consulta de crachás ativos e inativos
* Gerenciamento de lojas
* Controle de acesso baseado em perfil e setor
* Integração com pagamentos
* Envio de e-mails transacionais

---

## Fluxo de aprovação

Uma das principais partes do sistema é o controle do processo de aprovação.

Uma solicitação pode passar por diferentes responsáveis de acordo com o tipo de usuário e seu vínculo com a organização.

De forma simplificada:

```text
Usuário
   ↓
Solicitação de crachá
   ↓
Gestor responsável
   ↓
Segurança
   ↓
Crachá aprovado
```

O sistema registra informações relacionadas às aprovações e rejeições, permitindo maior rastreabilidade durante o processo.

---

## Perfis e permissões

O PantheraID trabalha com diferentes tipos de usuário, cada um com permissões específicas dentro da plataforma.

Entre os perfis existentes estão:

* Colaborador de loja
* Gestor de loja
* Usuário vinculado à academia (Alunos)
* Administração
* Vigilância
* Chefe de segurança
* Super administrador

As páginas, ações e informações disponíveis são controladas conforme o perfil e, quando necessário, o setor do usuário.

---

## Crachá digital

Após a conclusão do processo de aprovação, o sistema gera o crachá do usuário.

Cada crachá possui informações relacionadas ao usuário, sua solicitação e período de validade.

Os crachás podem assumir estados como:

```text
ACTIVE
EXPIRED
REVOKED
```

Também existe controle para impedir que um usuário mantenha múltiplos crachás ativos simultaneamente.

---

## Validação por QR Code

Os crachás podem ser validados através de QR Code.

Usuários autorizados, como profissionais da segurança, podem utilizar a câmera do dispositivo para realizar a leitura.

Após a leitura, o sistema consulta o crachá e verifica informações como:

* existência do crachá;
* status atual;
* período de validade;
* revogação;
* vínculo com o usuário.

Isso permite que a validação seja realizada rapidamente em pontos de acesso.

---

## Verificação de identidade

Antes de determinadas operações, o usuário pode precisar realizar uma etapa de verificação.

O sistema permite o envio de documento e utiliza OCR para analisar seu conteúdo.

Atualmente, essa funcionalidade possui integração com o **Google Cloud Vision**.

---

## Tecnologias

### Frontend

* React
* TypeScript
* Vite
* React Router
* Axios
* CSS Modules
* Lucide React
* React Toastify
* HTML5 QR Code
* PWA

### Backend

* Node.js
* Express
* JavaScript
* Zod
* JWT
* bcrypt
* Multer
* Helmet
* Express Rate Limit
* Node Cron

### Banco de dados e armazenamento

* PostgreSQL
* Supabase
* Supabase Storage

### Integrações

* Google Cloud Vision
* Mercado Pago
* Resend

---

## Arquitetura

A aplicação é dividida em frontend e backend independentes.

```text
┌─────────────────────────────┐
│          Frontend           │
│   React + TypeScript + Vite │
└──────────────┬──────────────┘
               │
               │ HTTP / API
               ▼
┌─────────────────────────────┐
│           Backend           │
│       Node.js + Express     │
│                             │
│  Autenticação               │
│  Regras de negócio          │
│  Controle de acesso         │
│  Integrações                │
└──────────────┬──────────────┘
               │
               ▼
┌─────────────────────────────┐
│          Supabase           │
│                             │
│  PostgreSQL                 │
│  Storage                    │
└─────────────────────────────┘
```

O frontend é responsável pela interface e interação com o usuário, enquanto o backend concentra autenticação, autorizações, validações, regras de negócio e comunicação com serviços externos.

---

## Segurança

Algumas das medidas implementadas atualmente incluem:

* Hash de senhas com bcrypt
* Autenticação utilizando JWT
* JWT armazenado em cookie HTTP-only
* Proteção de rotas
* Controle de acesso baseado em roles
* Controle adicional baseado em setores
* Validação de dados
* Rate limiting em rotas sensíveis
* CORS
* Helmet
* Validação de permissões no backend

A segurança da aplicação continua sendo revisada durante o desenvolvimento.

---

## Automação

O backend possui tarefas agendadas para executar determinadas regras automaticamente.

Um dos casos é a verificação periódica da validade dos crachás.

Quando um crachá ultrapassa sua data limite, seu estado pode ser atualizado automaticamente para expirado sem necessidade de intervenção manual.

---

## Screenshots

> As imagens abaixo serão atualizadas conforme a evolução da interface.

### Dashboard

<img width="878" height="1791" alt="image" src="https://github.com/user-attachments/assets/36923860-a003-4186-a979-9bf7cc9d37e8" />


### Solicitação de crachá

<img width="460" height="1600" alt="image" src="https://github.com/user-attachments/assets/7f52ca51-087d-4909-a9e2-1c535960b1c8" />


### Aprovação de solicitações

<img width="415" height="831" alt="image" src="https://github.com/user-attachments/assets/87b56291-4880-4efa-a836-1d4e6855f51c" />


### Validação por QR Code

<img width="884" height="1779" alt="image" src="https://github.com/user-attachments/assets/a25aeea9-2e2e-4681-a55b-59825e9c142c" />


### Gerenciamento de crachás

<img width="308" height="632" alt="image" src="https://github.com/user-attachments/assets/052cb985-507c-4b05-bd51-0f2552a51dc1" />

---

## Estrutura interna

O projeto original possui uma estrutura dividida aproximadamente da seguinte maneira:

```text
/
├── frontend/
│   └── src/
│       ├── Pages/
│       ├── components/
│       ├── contexts/
│       ├── routes/
│       └── services/
│
└── backend/
    └── src/
        ├── config/
        ├── jobs/
        ├── middlewares/
        ├── modules/
        ├── schemas/
        ├── services/
        └── utils/
```

Essa organização busca separar as responsabilidades e facilitar a manutenção conforme o sistema cresce.

---

## Status do projeto

🚧 **Em desenvolvimento**

O PantheraID ainda está sendo desenvolvido e aprimorado.

Algumas funcionalidades podem passar por alterações de arquitetura, interface ou regras de negócio durante a evolução do projeto.

Entre os pontos que continuam sendo trabalhados estão melhorias de experiência do usuário, segurança, testes e evolução das integrações existentes.

---

## Objetivo do projeto

Além de solucionar um problema real de gerenciamento de identificação e acesso, o PantheraID também representa a aplicação prática de conceitos de desenvolvimento full stack, como:

* arquitetura frontend/backend;
* modelagem de banco de dados;
* autenticação e autorização;
* regras de negócio;
* integração com APIs externas;
* armazenamento de arquivos;
* processamento de imagens;
* QR Codes;
* tarefas automatizadas;
* desenvolvimento responsivo;
* organização de uma aplicação em crescimento.

---

## Código-fonte

O código-fonte do PantheraID está atualmente armazenado em um **repositório privado**.

Este repositório público existe para documentar o desenvolvimento, apresentar as funcionalidades e demonstrar a evolução do projeto sem expor sua implementação completa.

---

## Sobre

O PantheraID é um projeto em desenvolvimento e novas funcionalidades, melhorias e alterações serão adicionadas conforme a aplicação evolui.

