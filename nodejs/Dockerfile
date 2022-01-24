# ------------------------ Common Image Base ------------------------
FROM node:16.13.1-alpine AS common

WORKDIR /usr/src/app

COPY package*.json ./

COPY . .

# ---------------------------- Dev Image ----------------------------
FROM common AS development

RUN npm install glob rimraf

RUN npm install --silent

RUN npm run build

# ---------------------------- Test Image ----------------------------
FROM development AS tests

ENV NODE_ENV=test

CMD ["npm", "test"]

# ---------------------------- Prod Image ----------------------------
FROM node:16.13.1-alpine as production

RUN apk add dumb-init

ENV NODE_ENV=production

RUN npm install --only=production --silent

COPY --from=development /usr/src/app/dist ./dist

EXPOSE 3000

CMD ["dumb-init", "npm", "start"]
