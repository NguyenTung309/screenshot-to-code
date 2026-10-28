FROM node:22-bullseye-slim

WORKDIR /app

ENV PUPPETEER_SKIP_DOWNLOAD=true

COPY package.json pnpm-lock.yaml /app/

RUN corepack enable && corepack prepare pnpm@latest --activate && pnpm install --frozen-lockfile

COPY ./ /app/

EXPOSE 5173

CMD ["pnpm", "dev", "--host", "0.0.0.0"]