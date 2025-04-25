FROM node:20-alpine3.19 AS base

# Install pnpm
RUN corepack enable && corepack prepare pnpm@latest --activate

# Set working directory
WORKDIR /app

# Copy root files needed for install
COPY package.json pnpm-workspace.yaml ./
COPY pnpm-lock.yaml ./

# Copy source code
COPY apps/backend ./apps/backend

# Install dependencies without frozen lockfile
RUN pnpm install --no-frozen-lockfile

# Set working directory to backend
WORKDIR /app/apps/backend

# Generate Prisma client
RUN npx prisma generate

# Build the app
RUN pnpm build

# Start the app
CMD ["pnpm", "start"]