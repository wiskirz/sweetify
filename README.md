# Sweetify - SweetAlert for Rails

[![Gem](https://img.shields.io/gem/v/sweetify.svg?style=flat-square)](https://rubygems.org/gems/sweetify) 
[![Build Status](https://travis-ci.org/wiskirz/sweetify.svg?branch=master)](https://travis-ci.org/wiskirz/sweetify)

This gem allows you to use [SweetAlert](http://t4t5.github.io/sweetalert/) for your flash messages.
_See the examples below, to see how to use it_

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'sweetify'
```

And then execute:

```bash
$ bundle
```


Add this line to your application.scss

```css
@import 'sweetalert';
```


Add this line to your application.js:

```js
//=require sweetalert
```


Next add the following line to the bottom of your application's layout file:

```html 
...

<%= render 'sweetify/alert' %>

</body> </html>
```

**You must restart your rails server after installing the gem**

## Usage
You can now easily create alerts in your controllers with any of the following methods provided by **Sweetify**:
```ruby
# Base Method, no type specified
sweetalert(text, title = '', opts = {})

# Additional methods with the type already defined
sweetalert_info(text, title = '', opts = {})
sweetalert_success(text, title = '', opts = {})
sweetalert_error(text, title = '', opts = {})
sweetalert_warning(text, title = '', opts = {})
```

## Example Usage
```ruby
# POST /resource
def create
    sweetalert_success('Your resource is created and available.', 'Successfully created', persistent: 'Awesome!')
    redirect_to resource_path
end
```

That would look like this after the redirect:

![Example Alert](http://i.imgur.com/3WMvk0y.png)


## Options
**By default, all alerts will dismiss after a sensible default number of seconds.**

Default Options set by **Sweetify**:
```ruby
{
    showConfirmButton: false,
    timer: 2000,
    allowOutsideClick: true,
    confirmButtonText: 'OK'
}
```

The following special options provided by **Sweetify** are available:
```ruby
# Shows the alert with a button, but will still close automatically
sweetalert('Text', 'Title', button: true)
sweetalert('Text', 'Title', button: 'Awesome!') # Custom text for the button

# Shows the alert with a button and only closes if the button is pressed
sweetalert('Text', 'Title', persistent: true)
sweetalert('Text', 'Title', persistent: 'Awesome!') # Custom text for the button
```

You also can use any other available option that [SweetAlert accepts](http://t4t5.github.io/sweetalert/):
```ruby
sweetalert_info('Here is a custom image', 'Sweet!', imageUrl: 'images/thumbs-up.jpg', timer: 5000)
```


## Contributing
Everyone is encouraged to help improve this project. Here are a few ways you can 
help:

- [Report bugs](https://github.com/atrox/sweetify/issues)
- Fix bugs and [submit pull requests](https://github.com/atrox/sweetify/pulls)
- Write, clarify, or fix documentation
- Suggest or add new features

