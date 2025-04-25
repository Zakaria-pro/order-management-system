# Order Management System

A modern full-stack application built with Next.js and NestJS in a monorepo structure using PNPM workspaces.

## Tech Stack

### Frontend

- Next.js 14 (React)
- TypeScript
- Tailwind CSS
- Running on port 3000

### Backend

- NestJS
- TypeScript
- PostgreSQL
- Running on port 3001

## Project Structure

```
order_management/
├── apps/
│   ├── frontend/     # Next.js application
│   └── backend/      # NestJS application
├── packages/         # Shared packages
├── pnpm-workspace.yaml
└── package.json
```

## Prerequisites

- Node.js 20.x or later
- PNPM 10.x or later
- PostgreSQL (for backend)

## Getting Started

1. **Install PNPM** (if not already installed):

```bash
npm install -g pnpm
```

2. **Clone the repository**:

```bash
git clone https://github.com/your-username/order_management.git
cd order_management
```

3. **Install dependencies**:

```bash
pnpm install
```

4. **Set up environment variables**:

```bash
# Copy example env files
cp apps/backend/.env.example apps/backend/.env
cp apps/frontend/.env.example apps/frontend/.env
```

5. **Start development servers**:

```bash
pnpm dev
```

This will start:

- Frontend at http://localhost:3000
- Backend at http://localhost:3001

## Available Scripts

- `pnpm dev` - Start all applications in development mode
- `pnpm build` - Build all applications
- `pnpm start` - Start all applications in production mode
- `pnpm test` - Run tests across all applications
- `pnpm lint` - Run linting across all applications

## Adding Dependencies

To add a dependency to a specific workspace:

```bash
pnpm add <package> --filter <workspace-name>
```

Example:

```bash
pnpm add axios --filter @order-management/frontend
```

## Docker Setup

### Prerequisites

- Docker
- Docker Compose

### Running with Docker

1. **Start the entire stack**:

```bash
docker-compose up -d
```

This will start:

- Frontend at http://localhost:3000
- Backend at http://localhost:3001
- PostgreSQL at localhost:5432

2. **View logs**:

```bash
docker-compose logs -f
```

3. **Stop the stack**:

```bash
docker-compose down
```

4. **Stop and remove volumes**:

```bash
docker-compose down -v
```

### Database Connection Details

- Host: localhost
- Port: 5432
- Username: postgres
- Password: postgres
- Database: order_management


