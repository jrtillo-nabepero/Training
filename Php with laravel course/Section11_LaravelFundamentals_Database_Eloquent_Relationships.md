# Section 11: Laravel Fundamentals - Database Eloquent Relationships

### Eloquent Relationships

- Laravel features Eloquent, an object-relational mapper (ORM) that simplifies database interaction. Each database table has a corresponding "Model" that interacts with that table when using Eloquent.

### One-to-One Relationship:

- In a one-to-one relationship, each record in one table is linked to exactly one record in another table. In Eloquent, you define this relationship using the hasOne() method on the parent model and the belongsTo() method on the child model.

### One-to-Many Relationship:

- In a one-to-many relationship, each record in one table can be connected to multiple records in another table. In Eloquent, this relationship is defined using the hasMany() method on the parent model and the belongsTo() method on the child model.

### Many-to-Many Relationship:

- In a many-to-many relationship, each record in one table can be linked to multiple records in another table, and vice versa. In Eloquent, you define this relationship using the belongsToMany() method on both models.

### Polymorphic:

- A polymorphic relationship allows a child model to be associated with more than one type of model through a single relationship.
