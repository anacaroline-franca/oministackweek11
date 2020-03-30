## Backend

### Database tables

This project contains two tables: ongs and incidents.

| ongs  |
| ------------- | 
| id  | 
| name (string) | 
| email (string) | 
| whatsapp (string) | 
| city (string) | 
| uf (string) | 

| incidents  |
| ------------- | 
| id  | 
| title (string) | 
| description (string) | 
| value (decimal) | 
| ong_id (foreign_key) | 

### Endpoints

**POST /incidents**

- URL: http://localhost:3333/incidents

Request
~~~~
Header: {
  Authorization: <ong_id>
}

Body:
{ 
   "title": "Title Example" ,
   "description": "My incident description",
   "value": 123,
}
~~~~
Response
~~~~
{
  id: 12345
}
~~~~

**GET /incidents**

- URL: http://localhost:3333/incidents?page=1

Response
~~~~
Header: {
  X-Total-Count: 1
}

Body:
[
   {
        "id": 10,
        "title": "My title",
        "description": "Thsi is it",
        "value": 123.6,
        "ong_id": "8428639f",
        "name": "MY ONG Example",
        "email": "email@test.com",
        "whatsapp": "000000000",
        "city": "Recife",
        "uf": "PE"
    },
]
~~~~

**DELETE /incidents**

- URL: http://localhost:3333/incidents/{id}

Request
~~~~
Header: {
  Authorization: <ong_id>
}
~~~~
Response
~~~~
{
}
~~~~

**POST /ong**

- URL: http://localhost:3333/ongs

Request
~~~~
Body:
{ 
    "name": "MY ONG Example",
    "email": "email@test.com",
    "whatsapp": "000000000",
    "city": "Recife",
    "uf": "PE"
}
~~~~
Response
~~~~
{
  id: 12345
}
~~~~

**GET /profile**

- URL: http://localhost:3333/profile

Request
~~~~
Header: {
  Authorization: <ong_id>
}
~~~~
Response
~~~~
{
  [
    "id": 1,
    "title": "Title Example" ,
    "description": "My incident description",
    "value": 123,
  ]
}
~~~~

**POST /session**

- URL: http://localhost:3333/session

Request
~~~~
Body:
{ 
   "id": 123,
}
~~~~
Response
~~~~
{
  id: <Ong name>
}
~~~~

### Dependences
- **celebrate** -> Used for request validation
- **cors-env** -> Used to set environment variable
- **express** -> Web application framework
- **knex** -> SQL Query Builder
- **sqllite3** -> DB
- **nodemon** -> Used for automatically restarting the node application when file changes in the directory are detected.
- **supertest** -> Used for requisitions on integration tests 
- **jest** -> Test
