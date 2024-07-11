# Section 9: Laravel Fundamentals - Database Migrations

### CRUD

- CRUD stands for Create, Read, Update, and Delete - the four basic operations used to manage data in a database. Laravel provides powerful tools to implement CRUD operations with ease.

**Create**

- To create a new record in the database, you need to define a route, a controller method, and a view that displays a form to collect the required data. In the controller method, you can use the `create()` method of the model to create a new instance of the resource and save it to the database.

**Read**

- To display all records or a specific record from the database, you can define a route and a controller method that fetches the data from the database using the model's `all() or find()` method. You can then pass the data to a view to display it to the user.

**Update**

- To update an existing record, you need to define a route, a controller method, and a view that displays a form with the current data. In the controller method, you can use the `update()` method of the model to update the record in the database.

**Delete**

- To delete a record, you need to define a route and a controller method that fetches the record from the database using the model's `find()` method and deletes it using the `delete()` method.
