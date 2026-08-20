FROM node:20-alpine

WORKDIR /app
COPY package.json ./
COPY src ./src
COPY configs ./configs
RUN mkdir -p /app/state && chown -R node:node /app

USER node
ENV NODE_ENV=production
EXPOSE 18110
CMD ["sh", "-c", "test -f /app/state/personality.json || cp /app/configs/personality.json /app/state/personality.json 2>/dev/null; exec node src/server.js"]
