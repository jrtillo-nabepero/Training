# Section 14: Database Eloquent - One to Many

**One to Many**

- A one-to-many relationship can be defined between two models using the `hasMany` and `belongsTo` methods.

**Guide to Remember**

- For example, let's say we have two models: User and Post. Each user can have many posts, but each post belongs to only one user.

```PHP

//CREATE
Route::get('/create', function(){

    $user = User::findOrFail(1);

    $post = new Post(['title'=>'First Post', 'body'=>'This is body']);

    $user->posts()->save($post);

});
//READ
Route::get('/read', function(){

    $user = User::findOrFail(1);

    foreach($user->posts as $post){

        echo $post->title . "<br>";

    }

});
//UPDATE
Route::get('/update',function(){

    $user = User::find(1);

    $user->posts()->whereId(1)->update(['title'=>'I love laravel','body'=>'This is awesome']);

});
//DELETE
Route::get('/delete',function(){

    $user = User::find(1);

    $user->posts()->whereId(1)->delete();

});

```
