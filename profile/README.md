# docker-compose

- Create a new folder
- Create a new file docker-compose.yml
- Copy the code and below and paste it into the file your just created.
- Start a new terminal into folder and run a this comand ```docker-compose-up``` or ```docker-compose-up -D``` to don't show the logs
- Create DB's references for each microservices

### Databases
- ms_stores
- ms_customers

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
