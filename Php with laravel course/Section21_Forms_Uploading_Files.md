# Section 21: Forms Uploading Files

### Uploading Files

- Laravel made uploading files easy because of its functions. Ive learned how to read or upload files from client.

**Sample code in the controller for uploading files**

```PHP
public function update(User $user){

        $inputs = request()->validate([
            'name' => ['required', 'string', 'max:255'],
            'email' => ['required', 'email', 'max:255'],
            'password' => ['min:6', 'max:255', 'confirmed']
        ]);

        if(request('avatar')){
            $inputs['path'] = request('avatar')->store('images');
        }

        // dd($inputs);
        $user->update($inputs);

        return back();
    }

```
