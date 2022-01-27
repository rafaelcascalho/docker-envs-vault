# ------------------------ Common Image Base ------------------------
FROM node:16.13.1-alpine3.14 AS common

WORKDIR /usr/src/app

COPY package*.json ./

COPY . .

# ---------------------------- Dev Image ----------------------------
FROM common AS development

RUN npm install -g typescript && \
    npm install --silent && \
    npm run build

# ---------------------------- Prod Image ----------------------------
FROM node:16.13.1-alpine3.14 as production

RUN apk add dumb-init --no-cache && \
    npm install --only=production --silent

COPY --from=development /usr/src/app/dist ./dist

EXPOSE 3000

CMD ["dumb-init", "npm", "start"]
