# Section 18: Forms And Validation

### Forms and Validation

**Forms**

- Forms enable users to enter data into a web application via an intuitive interface.
- Laravel offers various tools for building forms, simplifying form creation and submission handling.
- Laravel's form helpers can generate form HTML, including input fields, labels, and buttons.

**Validation**

- Validation ensures that form-submitted data adheres to specific criteria or requirements.
- Laravel features a robust validation system for easily defining rules for form inputs.
- You can set rules to check if inputs are required, meet length or format criteria, or match specific values.
- Laravel's validation system includes numerous built-in rules and supports the creation of custom validation rules.

```PHP
//OLD Syntax:
Route::resource('/posts','PostsController');

//NEW Syntax:

Route::resource('/posts',PostsController::class);

```

**CSRF PROTECTION**

- Cross-site request forgeries are a type of malicious exploit whereby unauthorized commands are performed on behalf of an authenticated user.
  Preventing CSRF Requests

- Laravel automatically generates a CSRF "token" for each active user session managed by the application. This token is used to verify that the authenticated user is the person actually making the requests to the application. Since this token is stored in the user's session and changes each time the session is regenerated, a malicious application is unable to access it.
  ///The current session's CSRF token can be accessed via the request's session or via the csrf_token helper function:

```PHP
use Illuminate\Http\Request;

Route::get('/token', function (Request $request) {
    $token = $request->session()->token();

    $token = csrf_token();

    // ...
});

```
