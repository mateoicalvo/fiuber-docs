Tech Stack
==========

The following technologies were used to develop this project:

Programming Languages
---------------------

- Python 3.10.7
- Javascript ES6

Web Frameworks
--------------

FastAPI
~~~~~~~

**Website**: https://fastapi.tiangolo.com/

Most microservices were implemented using this python framework (in fact, all of them except the API Gateway and
the payments microservice)

We found using FastAPI very straightforward, its automatic API documentation and validations were really helpful.

Fastify
~~~~~~~

**Website**: https://www.fastify.io/

Given the technical requirement of using both Python and Javascript as backend languages, we decided Fastify was
a suitable choice for the API Gateway because of its features: extensibility and high performance being the most
important ones.

DBMS
----

PostgreSQL
~~~~~~~

**Website**: https://www.postgresql.org/

Users, Trips, and Pricing Rules were persisted using PostgreSQL.

MongoDB
~~~~~~~

**Website**: https://www.mongodb.com/

We used MongoDB for storing ratings and payments data.

PaaS
----

**Website**: https://www.heroku.com

All microservices were deployed to Heroku via Docker containers.
