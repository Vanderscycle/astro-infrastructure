FROM node:alpine as builder

# Install latest pnpm
RUN apk add curl && \
  curl -fsSL "https://github.com/pnpm/pnpm/releases/latest/download/pnpm-linuxstatic-x64" -o /bin/pnpm; chmod +x /bin/pnpm;

COPY . .
RUN pnpm i --prod --prefer-offline --frozen-lockfile && \
  pnpm run build

# TODO: add the final step from build
