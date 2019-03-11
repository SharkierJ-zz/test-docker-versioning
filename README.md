This is a simple microservices example that uses Ruby + Sinatra to provide a simple Products Service. Docker support is included for running locally or deploying to services

__Note:__ This isn't production-ready code. The service assumes no Mongo username/password, doesn't force SSL, or enforce security best practices. This is for demonstration and learning purposes only. 

# Running locally

Install the required Rubygems:

> bundle install

Set an environment variable to point to the location of your MongoDB instance (e.g. 127.0.0.01 for localhost, or the specific IP/hostname if not localhost)

> export MONGODB_ADDRESS=127.0.0.1

Run Sinatra:

> ruby products_service.rb

# Running locally using Docker

Use docker-compose to build the service and mongodb containers (takes a few minutes the first time):

> docker-compose build

Then start the the containers:

> docker-compose up


# Interacting with the Products Service

Use [Postman](https://www.getpostman.com) or [cURL](https://curl.haxx.se/) to directly interact with the API. 

Get a list of products (empty by default):

> curl -X GET http://127.0.0.1:4567/products

Add a new product:

> curl -X POST http://127.0.0.1:4567/products -F "name=My Product"
