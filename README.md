# Yape-Code-Challenge
### Tech Stack:
- NestJS
- Typescript
- GraphQL
- Kafka
- Postgres
- Docker

## Initial Setup

1. Root directory contains a `docker-compose.yml` file. Run `docker-compose up -d` to create docker containers in detached mode.
2. Go to directory `transaction-manager-ms`
    2.1. Run `npm i` to install dependencies.
    2.2. Create the .env file with the following values.

    2.2. Run `npm start:prisma` to generate prisma dependencies.
    2.3. Run `npm start:dev` to start the microservice.

3. Go to directory `anti-fraud-ms`
    3.1. Run `npm i` to install dependencies.
    3.2. Create the .env file with the following values.

    3.3. Run `npm start:dev` to start the microservice.


# GraphQL API Documentation

Open your browser and go to http://localhost:5001/graphql

### Create transaction
```graphql
mutation  {
  createTransaction(createTransactionInput:{
    accountExternalIdDebit: "c3281685-b097-4d9a-a284-ef232af5eb32" ,
    accountExternalIdCredit: "ca7a6efa-e39f-4650-af63-2e40455850ce",
    transferTypeId: 1,
    value: 999.9
  }){
    transactionExternalId,
    transactionType{name},
    transactionStatus{name},
    value,
    createdAt
  }
}
```


### Retrieve transaction
```graphql
query{
  retrieveTransactionById(id:"ca7a6efa-e39f-4650-af63-2e40455850ce"){
    transactionExternalId,
    transactionType{name},
    transactionStatus{name},
    value,
    createdAt
  }
}
```