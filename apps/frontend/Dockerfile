FROM node:20-alpine AS base

# Install pnpm
RUN corepack enable && corepack prepare pnpm@latest --activate

# Set working directory
WORKDIR /app

# Copy root files needed for install
COPY package.json pnpm-workspace.yaml ./
COPY pnpm-lock.yaml ./

# Copy source code
COPY apps/frontend ./apps/frontend

# Install dependencies without frozen lockfile
RUN pnpm install --no-frozen-lockfile

# Set working directory to frontend
WORKDIR /app/apps/frontend

# Start the app
CMD ["pnpm", "dev"]