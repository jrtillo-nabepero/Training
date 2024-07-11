# Section 29: Laravel Components

**Laravel Components**

- Components can take many forms, including libraries, modules, frameworks, and UI elements. Here are some examples of components:

- To create a class based component, you may use the make:component Artisan command.

`php artisan make:component Card`

The make:component command will also create a view template for the component. The view will be placed in the resources/views/components directory. When writing components for your own application, components are automatically discovered within the app/View/Components directory and resources/views/components directory, so no further component registration is typically required.

- If you would like to create an anonymous component (a component with only a Blade template and no class), you may use the --view flag when invoking the make:component command:
  `php artisan make:component forms.input --view`

The command above will create a Blade file at resources/views/components/forms/input.blade.php which can be rendered as a component via <x-forms.input />.

**Passing Data To Components**

- passing data to components is a common way to share information between different parts of an application.

- You may pass data to Blade components using HTML attributes. Hard-coded, primitive values may be passed to the component using simple HTML attribute strings. PHP expressions and variables should be passed to the component via attributes that use the : character as a prefix:
  `<x-alert type="error" :message="$message"/>`

````PHP
namespace App\View\Components;

use Illuminate\View\Component;

class Alert extends Component
{
    /**
     * The alert type.
     *
     * @var string
     */
    public $type;

    /**
     * The alert message.
     *
     * @var string
     */
    public $message;

    /**
     * Create the component instance.
     *
     * @param  string  $type
     * @param  string  $message
     * @return void
     */
    public function __construct($type, $message)
    {
        $this->type = $type;
        $this->message = $message;
    }

    /**
     * Get the view / contents that represent the component.
     *
     * @return \Illuminate\View\View|\Closure|string
     */
    public function render()
    {
        return view('components.alert');
    }
}

    //When your component is rendered, you may display the contents of your component's public variables by echoing the variables by name:


    <div class="alert alert-{{ $type }}">

        {{ $message }}

    </div>

    ```
````
