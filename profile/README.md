# docker-compose

- Create a new folder
- Create a new file docker-compose.yml
- Copy the code and below and paste it into the file your just created.
- Start a new terminal into folder and run a this comand ```docker-compose-up``` or ```docker-compose-up -D``` to don't show the logs
- Clone all repositories in this folder
- Create DB's references for each microservices
- [Front-end use this project to access the others microservices](https://github.com/test-ws-work/gateway-api-front-office)

### Databases
- ms_stores
- ms_customers
- ms_logists (but it is not necessary to create this, only run this comand ```npx prisma migrate dev``` into terminal)

```version: "3"
volumes: 
  ws-stores-db-data: 
  ws-stores:
    driver: local
networks: 
  ws-stores-network: 
services: 
  ws-stores: 
    image: 'postgres'
    environment:
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: postgres
      POSTGRES_DB: ws-stores-db
    ports: 
      - "5432:5432"
    volumes: 
      - ws-stores-db-data:/var/lib/postgresql/data
    networks: 
      - ws-stores-network
```
