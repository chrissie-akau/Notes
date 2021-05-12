API - Application Programming Interface -> not a "visual" interface, but a programming interface.  One computer talking to another computer.

RESTful APIS-> most common APIs, but there are others.  They are very popular due to their simplicity.  Many programming languages can use Restful APIs.  

Restaurant Analogy ->
    - API=Waiter -> they are your messenger who gives the Chef your order.  You and the chef are like two computers/servers/programs.  The waiter tells the Chef you want a pizza.  The Chef is the person who actually makes the pizza.  The waiter brings the pizza to you and you can consume the pizza any way you want.

SkyScanner Example ->
    - Put in all your information that you want to find like dates and location of where you want to go.  Skyscanner takes it and pushes your data to other computers/servers/systems to find data that matches your parameters.  
    - Looks like SkyScanner did a ton of work, but really it just sent your information to other computers/servers and they did all the hard work and SkyScanner is now just presenting that information to you.  This is a one to many relationship.  

What are RESTful APIs?
    - REpresentational State Transfer -> client computer is making a request to another computer for data or to take an action.
    - Information an API sends back is in JSON (JavaScript Object Notation) -> essentially an object with several key/value pairs and JSON is the standard for every programming language and API.  It is lightweight and a lot quicker than it's predecessor, XML.  XML is the older version and heavier API notation.  One benefit is it has contracts, so you know what value is where, as opposed to JSON, the value could be an integer, string, etc.  No way to really tell with JSON what data type the value is.
        ex. {
                name: "Tori Flynn",
                age: 33,
                dog: "Parker",
                car: "Toyota Highlander"
            }

GET Request ->
    - Most common type
    - Simply asking for data, not asking to perform a task
    - Request to GET data from another computer
    - Not creating, updating, or deleting data
        ex. loading a website by going to facebook.com
    HTTP Method: GET, CRUD Operation: Read, ex. URLS -> http://website.com/api/users or http://website.com/api/users/1
    - Restaurant Analogy -> asking the waiter for to see the menu

POST Request ->
    - Do not go through the standard URL, but use a URL as the endpoint
    - Ask another computer to create a resource
        ex. You are a new user to a website so you fill out your name, email, password, and hit Submit button and now you are a user of that website
    HTTP Method: POST, CRUD Operation: Create, ex. URLS -> http://website.com/api/users
    - Restaurant Analogy -> Chef creating pizza for you after you ordered a pizza

DELETE Request ->
    - Do not go through the standard URL, but use a URL as the endpoint
    - Ask another computer to delete a single resource or a list of resources.
    - Use with caution!  Could configure to have someone able to delete all our users instead of a single profile
    HTTP Method: DELETE, CRUD Operation: Delete, ex. URL -> specific w/HTTP Delete http://website.com/api/user/1
    - Restaurant Analogy -> Waiter brings your bill and charges you twice for a pizza, even though you ordered one.  You ask them to take off the second charge.

PATCH Request ->
    - Do not go through the standard URL, but use a URL as the endpoint.
    - Ask another computer to update a piece of a resource
    - Patch requests are not fully supported by all browsers/frameworks, so fall back on PUT Request
        ex. Updating a user's first name
    HTTP Method: Patch, CRUD Operation: Partial Update/Modify, ex. URL -> specific w/HTTP Patch http://website.com/api/users/1/
    - Restaurant Analogy -> Waiter brings bill and you're mischarged for the pizza, $24 instead of $14, get rid of the one price and update it.

PUT Request ->
    - Do not go through the standard URL, but use a URL as the endpoint.
    - Ask another computer to update an entire resource
    - If resource doesn't exist, API might decide to CREATE (CRUD) the resource
    HTTP Method: Put, CRUD Operation: Update/Replace, ex. URL -> specific w/HTTP Put http://website.com/api/user/1/
    - Restaurant Analogy -> Get bill and there's a steak, but no pizza.  Need to delete the entire steak and replace with pizza.

Consuming APIs ->
    - APIs will return either JSON or XML (see above for more info on both)

Common API Responses ->
    - Request data from a server using GET, PATCH, POST, PUT or DELETE
    - Response will always come as an HTTP Status Code -> tells you what's wrong or right

    200s Healthy Responses ->
        - 200 - Ok - GET -> request accepted
        - 201 - Created - POST -> resources created
        - 202 - Accepted -> accepted but not done processing, might go into a queue
    
    300s Redirect Responses ->
        - 301 - Moved Permanently -> endpoint permanently changed, update your endpoint.
        - 302 - Found -> endpoint you're accessing is temporarily moved somewhere else
    
    400s Client Responses -> something on our end not right
        - 400 - Bad Request -> server cannot or will not process your request.  Normally due to bad API keys, or invalid payload
        - 401 - Unauthorized -> not allowed here.  Normally due to missing authentication credentials.
        - 403 - Forbidden -> Server understands your request but won't execute it.  API keys might not have the correct permissions or it might be trying to use an endpoint you don't have access to.
        - 404 - Not Found -> Nothing Here
        - 405 - Method Not Allowed -> wrong HTTP Method.  Endpoint might be accepting only GET requests and you might be POSTing instead.  
    
    500s Server Responses -> not on you and out of your control
        - 500 - Internal Server Error -> server had a problem and couldn't process your request.
    
API Security ->
    - API Keys -> pass words, your authentication credentials.  Token is usually generated with an API key.

Good Resources -> 
    - https://restfulapinet/http-methods/
    - https://httpstatuses.com/

