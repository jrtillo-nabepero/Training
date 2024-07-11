# Section 5: Laravel Fundamentals - Controllers

### Controllers

- Controller namespaces help organize controllers into subdirectories.
- In Laravel, controllers manage user requests and generate appropriate responses.
- Resource controllers can automatically create CRUD routes and methods for a specific model.

**Creating Controller**

- php artisan make
  'Name_of_The_Controller': This command is recommended for creating controllers instead of manually creating files.

- php artisan make
  --resource 'Name_of_The_Controller': This command creates a controller with built-in CRUD functionality.
