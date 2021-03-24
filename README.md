# Our Neighbourhood API

### About

Our Neighbourhood API allows you to store and look up data on your local neighbourhood including people's address, number of people in each household, their names and age.

Our Neighbourhood API is REST-based, mainly using POST and GET.

Our Neighbourhood API returns reults in various formats including JSON.

### Base 
https://our-neighbourhood-api/




### Authentication 
To run a successful API call, you will need to pass your API Key in the apikey query parameter. Your API Key should automatically appear in all URLs throughout this portal.

Example: https://our-neighbourhood-api/peoplejson?apikey={apikey}

Without a valid API Key, you will receive a 401 Status Code with the following response:



### Errors

When an error occurs during an API request, you will receive:

An HTTP error status (in the 400-500 range)
A JSON response containing more information about the error

A typical error response looks like this:
```{
"errors": [
{
"status": 404,
"title": "Route Not Found"
}
]
}```


### Adding information

Method: POST
Summary: add household
Description: add information about people and their households


### Neighbourhood Search

Method: GET
Summary: household search
Description: find households by searching their name, this will return the house, address and it's owner




Method: GET
Summary: people search
Description: find people within certain age brackets and with specific household sizes



### Field entries (schema)

CREATE TABLE person(
    person_id SERIAL PRIMARY KEY,
    first_name VARCHAR(45) NOT NULL,
    last_name VARCHAR(45) NOT NULL,
    age INT NOT NULL,
    
);


CREATE TABLE household(
    household_id SERIAL PRIMARY KEY,
    owner_first_name VARCHAR(45) NOT NULL,
    owner_last_name VARCHAR(45) NOT NULL,
    owner_age INT NOT NULL,
    street_address VARCHAR(40) NOT NULL,
    postcode VARCHAR (10) NOT NULL,
    number_people_in_household INT
    
);

![image (1)](https://user-images.githubusercontent.com/75622197/112303256-fc8b4980-8c93-11eb-9c43-29639c318513.png)

