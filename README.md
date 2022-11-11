# crud-operation-for-algodomain
Java Spring boot project on crud operations

The CRUD operation can be defined as user interface conventions that allow view, search, and modify information through computer-based forms and reports. CRUD is data-oriented and the standardized use of HTTP action verbs. HTTP has a few important verbs.

POST: Creates a new resource
GET: Reads a resource
PUT: Updates an existing resource
DELETE: Deletes a resource
Within a database, each of these operations maps directly to a series of commands. However, their relationship with a RESTful API is slightly more complex.

Standard CRUD Operation
CREATE Operation: It performs the INSERT statement to create a new record.
READ Operation: It reads table records based on the input parameter.
UPDATE Operation: It executes an update statement on the table. It is based on the input parameter.
DELETE Operation: It deletes a specified row in the table. It is also based on the input parameter.

Spring Boot provides an interface called CrudRepository that contains methods for CRUD operations. It is defined in the package org.springframework.data.repository. It extends the Spring Data Repository interface. It provides generic Crud operation on a repository. If we want to use CrudRepository in an application, we have to create an interface and extend the CrudRepository.

methods:
getAllProduct(): It returns a List of all products.
getProduct(): It returns a product detail that we have specified in the path variable. We have passed productid as an argument by using the annotation @PathVariable. The annotation indicates that a method parameter should be bound to a URI template variable.
deleteProduct(): It deletes a specific product that we have specified in the path variable.
saveProduct(): It saves the Product detail. The annotation @RequestBody indicates that a method parameter should be bound to the body of the web request.
update(): The method updates a record. We must specify the record in the body, which we want to update. To achieve the same, we have used the annotation @RequestBody.

Open the Postman and do the following:

Select the POST
Invoke the URL http://localhost:8080/product.
Select the Body
Select he Content-Type JSON (application/json).
Insert the data.
Click on the Send
When the request is successfully executed, it shows the Status:200 OK. It means the record has been successfully inserted in the database.

Open the browser and invoke the URL http://localhost:8080/h2-console. Click on the Connect button.
After clicking on the Connect button, we see the products table in the database.
Click on the product table and then click on the Run button. The table shows the data that we have inserted in the body.
Open the Postman and send a GET request with the URL http://localhost:8080/product. It returns the data that we have inserted in the database.
Let's send a GET request with the URL http://localhost:8080/product/{productid}.
Similarly, we can also send a DELETE request to delete a record.
Select the PUT
In the request body, paste the record which you want to update and make the changes.
lick on the Send
Now, move to the H2 console and see the changes have reflected or not.
