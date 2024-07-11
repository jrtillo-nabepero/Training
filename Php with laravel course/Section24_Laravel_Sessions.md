# Section 24: Laravel Sessions

### Sessions

- Sessions in Laravel provide a way to store user-specific data on the server and associate it with a unique session identifier stored on the client-side as a cookie.

**Sample code for session**

```php

public function destroy(Post $post){

        $this->authorize('update');

        $post->delete();

        // dd(back());
        Session::flash('message', 'Post was deleted!');
        return back();
    }

```
