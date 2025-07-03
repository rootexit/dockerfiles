FROM node:20-alpine
RUN corepack enable && corepack prepare pnpm@9.15.3 --activate && npm config set registry https://registry.npmmirror.com && pnpm config set registry https://registry.npmmirror.com