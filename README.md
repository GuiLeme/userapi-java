# userapi-java
User API CRUD to learn how to use JPA with Spring boot web.


Project Proposed by Digital innovation one.

## Routes, parameters and returns:

### Create:

The URI: http://localhost/api/v1/people 
Method: POST 
Body: 

 - Example of a valid body:
{
    "firstName": "Guilherme Pereira",
    "lastName": "Leme",
    "cpf": "379.232.751-14",
    "birthDate": "15-04-2000",
    "phones": [
        {
            "type": "MOBILE",
            "number": "(11)991000214"
        }
    ]
}

It is possible to alter this input to introduce more phones into the list, that later will be mapped by the Hibernate Framework and inserted in the Phones table.
Another comment that seems to be necessary to be made: The CPF must be a valid one. Here in Brazil, we have a validation rule for the CPF which I am not covering in this readme file.
But be aware that we have duzens of sites that generate those, one that I recommend and it is pretty straight forward is: geradorcpf.com

Return: 
{
    "message": "Created person with id: 4"
}

Clearly, the Id changes as you create more and more data.

### Read:

The URI: http://localhost/api/v1/people
Alternative URI: http://localhost/api/v1/people/{id}
Method: GET
Body:

Null

Returns: For the first URI, the return must be a list of Json, and for the second, only one Json, the one specified in the route.


### Update:

The URI: http://localhost/api/v1/people/{id}
Method: PUT
Body:

 - Example of body:
 
{
    "id": 1,
    "firstName": "Guilherme Pereira",
    "lastName": "Leme",
    "cpf": "379.232.751-14",
    "birthDate": "15-04-2000",
    "phones": [
        {
            "id": 1,
            "type": "MOBILE",
            "number": "(11)991000214"
        }
    ]
}

Don't forget the Id's that must be specified not only on the route, but also in the JSON's body.

Return:
{
    "message": "Updated person with id: 4"
}

### Delete:

The URI: http://localhost/api/v1/people/{id}
Method: DELETE
Body:
Null

Return:
Null


#### Notes:

When the Id specified on the Route does not exists, the return is an error 404: Person not found.
