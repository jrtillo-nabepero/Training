# Section 12: Laravel Fundamentals - Database Tinker

**Tinker**

- Laravel Tinker is an interactive REPL (Read-Eval-Print Loop) for the Laravel framework, utilizing the PsySH package.
- Tinker enables command-line interaction with your entire Laravel application, including Eloquent models, jobs, events, and other components.
- To start the Tinker environment, execute the tinker command using Artisan.

Simple Exercise :

```PHP


$ php artisan tinker
Psy Shell v0.11.1 (PHP 8.1.1 — cli) by Justin Hileman
>>> $post = App
PHP Parse error: Unexpected character "" (ASCII 31) on line 1
>>> $post = App\Models\Post::create(['title'=>'PHP post from tinker' , 'body'=>'This is body']) ;
=> App\Models\Post {#3521
     title: "PHP post from tinker",
     body: "This is body",
     updated_at: "2024-07-05 03:50:49",
     created_at: "2024-07-05 03:50:49",
     id: 3,
   }
>>> $post = new App\Models\Post
=> App\Models\Post {#3519}
>>> $post->title = "New title from this object"
=> "New title from this object"
>>> $post->body = "This is new content 2"
=> "This is new content 2"
>>> $post
=> App\Models\Post {#3519
     title: "New title from this object",
     body: "This is new content 2",
   }
>>> $post->save();
=> true
>>> $post
=> App\Models\Post {#3519
     title: "New title from this object",
     body: "This is new content 2",
     updated_at: "2024-07-05 03:57:01",
     created_at: "2024-07-05 03:57:01",
     id: 4,
   }
>>> $post = App\Models\find(6);
PHP Error:  Call to undefined function App\Models\find() in Psy Shell code on line 1
>>> $post = App\Models\Post::find(6);
=> null
>>> $post = App\Models\Post::find(3);
=> App\Models\Post {#3536
     id: 3,
     title: "PHP post from tinker",
     body: "This is body",
     created_at: "2024-07-05 03:50:49",
     updated_at: "2024-07-05 03:50:49",
     is_admin: 0,
     deleted_at: null,
   }
>>> $post
=> App\Models\Post {#3536
     id: 3,
     title: "PHP post from tinker",
     body: "This is body",
     created_at: "2024-07-05 03:50:49",
     updated_at: "2024-07-05 03:50:49",
     is_admin: 0,
     deleted_at: null,
   }
>>> $post->delete()
=> true
>>> $post
=> App\Models\Post {#3536
     id: 3,
     title: "PHP post from tinker",
     body: "This is body",
     created_at: "2024-07-05 03:50:49",
     updated_at: "2024-07-05 04:04:25",
     is_admin: 0,
     deleted_at: "2024-07-05 04:04:25",
   }
>>> $post->forcedelete()
=> true
>>> $post
=> App\Models\Post {#3536
     id: 3,
     title: "PHP post from tinker",
     body: "This is body",
     created_at: "2024-07-05 03:50:49",
     updated_at: "2024-07-05 04:04:25",
     is_admin: 0,
     deleted_at: "2024-07-05 04:04:25",
   }
>>> $post = App\Models\Post::onlyTrashed()
=> Illuminate\Database\Eloquent\Builder {#3506}
>>> $post->forcedelete()
=> 0

```
