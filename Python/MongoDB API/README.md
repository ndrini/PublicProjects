# Run 

On MongoDB API folder with

    $ docker-compose up


# Test

## 1 Backend 
That flask runs: 

    curl --request GET 'http://localhost:5001'

expected: 

    {"Status": "UP"}

## 2 DB

That port 5000 is available:

    $ curl localhost:5000

Expected answer: 

    It looks like you are trying to access MongoDB over HTTP on the native driver port.


That the database is available: 

    $ curl --request GET 'http://localhost:5001/mongodb' --header 'Content-Type: application/javascript' \
    --data-raw '{
    "database": "IshmeetDB",
    "collection": "people"
    }'

Expected list of users.
Error if the reponse is: 

    {"Error": "Please provide connection information"}



# Errors

  + no dababase initialization  "database"
    + the backend needs a database called "IshmeetDB" and a "collection" called "people"

  + not any communication between backend and mongodb
  

# ToDo 
- check real communication between flask and mongodb
- probably create the collection in mongodb 
