# Section 10: Laravel Fundamentals - Database Eloquent / ORM

### Eloquent

- Laravel includes Eloquent, an object-relational mapper (ORM) that makes it enjoyable to interact with your database. When using Eloquent, each database table has a corresponding "Model" that is used to interact with that table.

- Eloquent uses a convention-based approach for mapping model properties to database columns. For example, if you have a name property on your model, Eloquent will automatically map it to a name column in the corresponding database table.

- Eloquent supports relationships between models, such as one-to-one, one-to-many, and many-to-many relationships. You can define these relationships using methods on your model class, such as `belongsTo(), hasMany(), and belongsToMany()`.

- Eloquent has built-in support for soft deletes, which allows you to mark records as "deleted" without actually deleting them from the database. This can be useful for auditing purposes or for providing a "trash" feature in your application.

**PRIMARY KEYS**

- Eloquent will also assume that each model's corresponding database table has a primary key column named id. If necessary, you may define a protected $primaryKey property on your model to specify a different column that serves as your model's primary key:

**Soft Deleting**

- When models are soft deleted, they are not actually removed from your database. Instead, a deleted_at attribute is set on the model indicating the date and time at which the model was "deleted".
