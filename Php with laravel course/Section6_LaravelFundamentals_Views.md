# Section 6: Laravel Fundamentals - Views

### Views

- Views are used to generate the HTML that is sent to the user's web browser.

**BLADE**

- Blade provides convenient shortcuts for common PHP control structures, such as conditional statements and loops.

**Passing Data to View**

```PHP
public function index()
{
    $posts = Post::all();
    return view('home', ['posts' => $posts]);
}
```

**Commands**

```PHP
 {{}} use this instead of <?php echo " " in the blade file>
```
