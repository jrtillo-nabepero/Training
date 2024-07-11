# Section 13: Database Eloquent - One to One

**One to One**

- One to one is a relationship between two models using the `hasOne` and `belongsTo` methods.

**Guide to Remember**

- A good example is a `User` and `Profile`. Each user has one profile, and each profile belongs to one user.

```PHP
class User extends Model
{
    public function profile()
    {
        return $this->hasOne(Profile::class);
    }
}

class Profile extends Model
{
    public function user()
    {
        return $this->belongsTo(User::class);
    }
}

```

```PHP
/*
|--------------------------------------------------------------------------
| CRUD WITH ONE-TO-ONE RELATION
|--------------------------------------------------------------------------
|
*/
//Create
Route::get('/insert', function(){

    $user = User::findOrFail(1);

    $address = new Address(['name'=>'Bogart']);

    $user->address()->save($address);

});

//Read
Route::get('/read', function(){

    $user = User::findOrFail(1);

    echo $user->address->name;

});

//Update
Route::get('/update ', function(){

    $address = Address::whereUserId(1)-> first();

    $address->name = "asdasd123123";

    $address->save();

});

//Delete
Route::get('/delete',function(){

    $user = User::findOrFail(1);

    $user->address()->delete();

    return "Done";

});

```
