# Section 28: Data Seeding

**Factories & seeders**

- Factories and seeders are two concepts commonly used in software development, particularly in the context of database management and testing.

- A factory is a design pattern used to create objects in a flexible way, allowing for customization and dynamic creation of object instances. In the context of software development, a factory can be used to create and initialize objects with default or custom values.

- A seeder, on the other hand, is a tool used in database management to populate a database with test data. Seeders are typically used during the development and testing phase of a software project to create sample data for testing purposes.

```PHP
php artisan make:seeder UsersTableSeeder


 public function run()
    {
        DB::table('users')->insert([
            'name' => Str::random(10),
            'email' => Str::random(10).'@gmail.com',
            'password' => Hash::make('password'),
        ]);
    }

```

**Running Seeders**

```php artisan db:seed

php artisan db:seed --class=UserSeeder


php artisan migrate:fresh --seed
// drop all tables and re-run all of your migrations
```

**Factory**

- Manually specifying the attributes for each model seed is cumbersome. Instead, you can use model factories to conveniently generate large amounts of database records.

```
use App\Models\User;

/**
 * Run the database seeders.
 *
 * @return void
 */
public function run()
{
    User::factory()
            ->count(50)
            ->hasPosts(1)
            ->create();
}
```

**Calling Additional Seeders**

- In software development, seeders are often used to populate a database with initial or test data. In some cases, multiple seeders may be required to populate different parts of the database or to perform different types of data seeding. In Laravel, a popular PHP web application framework, you can call additional seeders from within another seeder by using the call() method.

- To call another seeder from within a seeder, you can use the call() method provided by Laravel's Seeder class. This method takes the name of the seeder class you wish to call as its first parameter. You can also pass additional parameters to the seeder class's constructor by passing an array of arguments as the second parameter to the call() method.

```
public function run()
{
    $this->call([
        UserSeeder::class,
        PostSeeder::class,
        CommentSeeder::class,
    ]);
}
```

- In summary, factories and seeders are both important tools in software development, with factories used to create objects and seeders used to populate databases with test data.
