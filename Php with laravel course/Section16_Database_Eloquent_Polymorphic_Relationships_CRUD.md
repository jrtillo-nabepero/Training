# Section 16: Database Eloquent - Polymorphic Relationships CRUD

### CRUD Operation

```PHP
Route::get('/create',function(){

    $staff = Staff::find(1);

    $staff->photos()->create([

    'path' => 'picture.jpg'

]);

});

Route::get('/read',function(){

    $staff = Staff::findOrFail(1);

    foreach($staff->photos as $photo){

        return $photo->path;
    }

});

Route::get('/update',function(){

    $staff = Staff::findOrFail(1);

    $photo = $staff->photos()->whereId(1)->first();

    $photo->path = "update picture.jpg";

    $photo->save();
});

Route::get('/delete', function(){

    $staff = Staff::find(1);
    $staff->photos()->where('imageable_id', $staff->id)->where('imageable_type', Staff::class)->delete();

});

Route::get('/assign', function(){

    $staff = Staff::findOrFail(1);

    $photo = Photo::findOrFail(3);

    $staff->photos()->save($photo);

});

Route::get('/unassign', function(){

    $staff = Staff::findOrFail(1);

    $staff->photos()->whereId(2)->update(['imageable_id'=>'','imageable_type'=>'']);

});

```
