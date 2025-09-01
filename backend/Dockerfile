###Stage 1
FROM node:21 as backend-builder

#setup the working dir
WORKDIR /app

#code
COPY . .

RUN npm i

### stage 2
FROM node:21-slim
WORKDIR /app

#copy the above stage as compressed
COPY --from=backend-builder /app .

COPY .env.sample .env

#port
EXPOSE 5000

#app
CMD ["npm","start"]
