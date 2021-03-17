# Run 

On MongoDB API folder with

    $ docker-compose up

# Test
That flask runs: 

    curl --request GET 'http://localhost:5001'

expected: 

    {"Status": "UP"}


That the database is available: 

    $ curl --request GET 'http://localhost:5001/mongodb' --header 'Content-Type: application/javascript' \
    --data-raw '{
    "database": "IshmeetDB",
    "collection": "people"
    }'

Expected list of users.
Error if the reponse is: 

    {"Error": "Please provide connection information"}


# ToDo 
- check real communication between flask and mongodb
- probably create the collection in mongodb 
