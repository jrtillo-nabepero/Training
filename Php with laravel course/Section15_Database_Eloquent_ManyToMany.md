# Section 15: Database Eloquent - Many to Many

**Many to Many**

**Syncing Association**

- To update a user's roles, use the `sync` method on the user's roles relationship. The `sync` method takes an array of role IDs to associate with the user, adjusting the associations by adding or removing roles to match the given IDs.

**Guide to Remember**

- User and Role, with a many-to-many relationship between them. Each user can have multiple roles, and each role can be assigned to multiple users.

**CRUD EXERCISE**

```PHP
//CREATE
Route::get('/create',function(){



    $user = User::find(1);
    $role = new Role(['name'=>'Administrator']);

    $user->roles()->save($role);

});

//READ
Route::get('/read',function(){

    $user = User::findOrFail(1);


    foreach($user->roles as $role ){

        echo $role->name;
    }


});

//UPDATE
Route::get('/update',function(){

    $user = User::findOrFail(1);

    if($user->has('roles')){

        foreach($user->roles as $role){

            if($role->name == 'Administrator'){

                $role->name = 'administrator';
                $role->save();
            }
        }

    }



});

//DELETE
Route::get('/delete',function(){

    $user = User::findOrFail(1);

    $user->roles()->delete();
        //specific deletion
    // foreach($user->roles as $role){
    //     $role->whereId(#deleted)->delete();
    // }
});

 //atach role to user if not attached it will create another record.
Route::get('/attach',function(){

    $user = User::findOrFail(1);

    $user->roles()->attach(2);

});

//detach what ever id you give and detach the id.

Route::get('/detach',function(){

    $user = User::findOrFail(1);

    $user->roles()->detach(2);

});


Route::get('/sync',function(){

    $user = User::findOrFail(1);

    $user->roles()->sync([1,2]);

});
```
