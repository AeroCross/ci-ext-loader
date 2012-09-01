## What is it?

By using **Presenters**, you'll be using logic (call methods, helpers, loops, etc.) to output HTML to you views. By using this loader, you can store all your presenters in a folder and easily load them and use them in your controllers and views.

## How to Use

To use this extension, is simple.

### Loading

Copy the `EXT_Loader.php` file to your `application/core` folder, and set your `$config['subclass_prefix']`. to EXT_ (or just rename the file with the value you want. EXT_ is just the default for this file, and MY_ for Codeigniter)

### Creating presenters

Create a `presenters` directory inside your `application` directory.

Inside you can create an unlimited number of presenters. The naming pattern is:

	application/presenters/name.php

And you'll be naming your classes:

	class NamePresenter {
		public class create($param) {
		
		}
	}

- Use a lowercased name as a script name.
- Use the same name, but with a uppercased initial and suffix "Presenter" as your class name

### Loading presenters

In your controllers, you can just call `$this->load->presenter('name')` and the presenter will be available as an object in `$this->presenter->name->create($param)`, inside your controllers and views.

Unlike a normal load(), the presenters are **namespaced** — that means that every presenter is inside the `$this->presenter` object. You can use any names you've used before in your models or libraries without any name collision.

The pattern would be: `$this->presenter->$name->$method($parameters)`.