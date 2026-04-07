# TypeScript Example (Multi-stage)

```docker {all|1-2|4-6|8-10|12-14|all}
FROM node:22-alpine AS builder

WORKDIR /app

COPY package.json pnpm-lock.yaml ./
RUN corepack enable && pnpm install --frozen-lockfile

COPY tsconfig.json ./
COPY src/ src/
RUN pnpm build

FROM node:22-alpine AS runner
WORKDIR /app

COPY --from=builder /app/dist ./dist
COPY --from=builder /app/node_modules ./node_modules
COPY package.json ./

EXPOSE 3000
HEALTHCHECK CMD wget -q --spider http://localhost:3000/health || exit 1

CMD ["node", "dist/main.js"]
```

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- Multi-stage build: builder compiles TypeScript, runner only has the compiled JavaScript.
- node:22-alpine: lightweight image based on Alpine Linux.
- corepack enable: enables pnpm without global installation.
- --frozen-lockfile: ensures reproducibility.
- COPY --from=builder: copies only the compiled artifacts, reducing the final image size.
- HEALTHCHECK: verifies the app is still running.
-->
