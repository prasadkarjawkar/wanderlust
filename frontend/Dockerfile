FROM node:21 as frontend-builder
#Set the working dir to /app
WORKDIR /app

COPY . .

RUN npm i

##stage 2 

FROM node:21-slim

WORKDIR /app
# Copy build assets and dependencies from frontend-builder stage
COPY --from=frontend-builder /app .

COPY .env.sample .env.local

EXPOSE 5173

CMD ["npm","run","dev","--","--host"]
