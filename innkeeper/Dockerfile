FROM node:20-alpine

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

RUN addgroup -S app && adduser -S app -G app
USER app

EXPOSE 4181

ENTRYPOINT ["node"]
CMD ["src/index.js"]

