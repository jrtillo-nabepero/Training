# Section 30: New Application

**LARAVEL 7**

- policies are classes that define authorization rules for a given model. Policies determine whether a user is authorized to perform a specific action on a model instance, such as creating, updating, or deleting it.

- To create a policy, you can use the make:policy Artisan command. For example, to create a policy for a Post model, you would run:

`php artisan make:policy PostPolicy --model=Post`

- This command will generate a PostPolicy class in the app/Policies directory.

- In the PostPolicy class, you can define authorization rules for various actions. For example, to allow only the user who created a post to update or delete it, you could define the update and delete methods as follows:

```PHP
public function update(User $user, Post $post)
{
    return $user->id === $post->user_id;
}

public function delete(User $user, Post $post)
{
    return $user->id === $post->user_id;
}
```

- In this example, the update and delete methods receive a User instance representing the authenticated user, and a Post instance representing the post being updated or deleted. The methods return true if the user is authorized to perform the action, and false otherwise.

- Once you have defined a policy, you can use it in your controllers or other classes to authorize actions on model instances. For example, to check if a user is authorized to update a post, you could use the authorize method in your controller:

```PHP

public function update(Request $request, Post $post)
{
    $this->authorize('update', $post);

    // Update the post
}
```

**Middleware Route**

- Gets Authentication before proceding to route

````
 Route::middleware('auth')->group(function(){

    Route::get('/admin', [App\Http\Controllers\AdminsController::class, 'index'])->name('admin.index');```

**Factory with relation**


```$ php artisan make:factory PostFactory --model=Post```

```PHP


<?php

namespace Database\Factories;

use Illuminate\Database\Eloquent\Factories\Factory;

/**
 * @extends \Illuminate\Database\Eloquent\Factories\Factory<\App\Models\Post>
 */
class PostFactory extends Factory
{
    /**
     * Define the model's default state.
     *
     * @return array
     */
    public function definition()
    {
        return [

            'title' => $this->faker->sentence,
            'body' => $this->faker->sentence,
            'post_image' => $this->faker->imageUrl('900','300'),
            //
        ];
    }
}
========================================================================
<?php

namespace Database\Seeders;

use Illuminate\Database\Console\Seeds\WithoutModelEvents;
use Illuminate\Database\Seeder;

use App\Models\Post;
use App\Models\User;

class DatabaseSeeder extends Seeder
{
    /**
     * Seed the application's database.
     *
     * @return void
     */
    public function run()
    {

      $user = User::factory(2)
        ->has(Post::factory())
        ->create();

    }
}
````
