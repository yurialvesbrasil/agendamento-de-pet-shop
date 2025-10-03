# Agendamento de Pet Shop

Sistema de agendamento para pet shop desenvolvido com Next.js 15, TypeScript e Prisma.

## 🚀 Tecnologias

### Frontend

- **Next.js 15** - Framework React com App Router
- **React 19** - Biblioteca para interfaces de usuário
- **TypeScript** - Tipagem estática
- **Tailwind CSS 4** - Framework CSS utilitário
- **shadcn/ui** - Biblioteca de componentes UI
- **Radix UI** - Componentes primitivos acessíveis
- **Lucide React** - Ícones
- **React Hook Form** - Gerenciamento de formulários
- **Zod** - Validação de schemas
- **date-fns** - Manipulação de datas
- **Sonner** - Notificações toast

### Backend & Database

- **Prisma** - ORM para TypeScript
- **PostgreSQL** - Banco de dados relacional
- **Docker** - Containerização do banco

### Ferramentas de Desenvolvimento

- **ESLint** - Linter para JavaScript/TypeScript
- **Prettier** - Formatador de código
- **Lefthook** - Git hooks
- **pnpm** - Gerenciador de pacotes

## 📋 Pré-requisitos

- Node.js 18+
- pnpm
- Docker e Docker Compose

## ⚙️ Configuração e Instalação

### 1. Clone o repositório

```bash
git clone <url-do-repositorio>
cd nextjs-pet-shop
```

### 2. Instale as dependências

```bash
pnpm install
```

### 3. Configure o banco de dados

```bash
# Inicie o PostgreSQL com Docker
docker-compose up -d

# Configure as variáveis de ambiente
cp .env.example .env.local
```

Adicione no arquivo `.env.local`:

```env
DATABASE_URL="postgresql://docker:docker@localhost:5432/petshop"
```

### 4. Configure o Prisma

```bash
# Execute as migrações
npx prisma migrate dev --name "init"

# Gere o cliente Prisma
npx prisma generate
```

### 5. Execute o projeto

```bash
pnpm dev
```

O projeto estará disponível em `http://localhost:3000`

## 🏗️ Estrutura do Projeto

```
src/
├── app/                 # App Router do Next.js
├── components/          # Componentes React
│   ├── ui/             # Componentes base (shadcn/ui)
│   └── ...             # Componentes específicos
├── lib/                # Utilitários e configurações
├── types/              # Definições de tipos TypeScript
├── utils/              # Funções utilitárias
└── styles/             # Estilos globais
```

## 🎨 Padrões de Projeto

- **Component Composition** - Componentes reutilizáveis com shadcn/ui
- **Type Safety** - Tipagem completa com TypeScript
- **Form Validation** - Validação com React Hook Form + Zod
- **Server Actions** - Ações do servidor do Next.js
- **Database ORM** - Prisma para acesso ao banco
- **Responsive Design** - Layout responsivo com Tailwind CSS

## 📱 Funcionalidades

- ✅ Agendamento de consultas para pets
- ✅ Visualização de agendamentos por período (manhã, tarde, noite)
- ✅ Formulário de agendamento com validação
- ✅ Interface responsiva e acessível
- ✅ Notificações toast para feedback

## 🎨 Design

Design baseado no Figma: [Agendamento de petshop](https://www.figma.com/design/H6yyhi4Dpurdaa4hmRrE14/Agendamento-de-petshop--Community-?node-id=3-376&p=f&t=96lliCoCQTZ1JT59-0)

## 📝 Scripts Disponíveis

```bash
pnpm dev          # Inicia o servidor de desenvolvimento
pnpm build        # Gera build de produção
pnpm start        # Inicia o servidor de produção
pnpm lint         # Executa o linter
pnpm format       # Formata o código com Prettier
pnpm validate:typecheck  # Verifica tipos TypeScript
```

## 🗄️ Banco de Dados

O projeto utiliza PostgreSQL com Prisma ORM. O schema define a tabela `appointments` com os campos:

- `id` - Identificador único
- `tutorName` - Nome do tutor
- `petName` - Nome do pet
- `phone` - Telefone de contato
- `description` - Descrição do serviço
- `scheduleAt` - Data e hora do agendamento
