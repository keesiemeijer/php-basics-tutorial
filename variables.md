# Variables.

Let's start with a thing called "variables". In most programming languages, a variable can hold a value. Variables in PHP start with a dollar sign `$` followed by the name of the variable. After creating a variable it can be reused throughout the code. 

```php
<?php $my_variable = 'I want to learn PHP'; ?>
```

As you can see, the `$my_variable` variable has a value of `I want to learn PHP`.

Values are assigned (added) to variables with the "equals" sign `=`

In PHP a "string" is a series of characters inside quotes. With this information we can say "The `$my_variable` variable is a string". More about strings later.

Let's say we wanted to display the value of a variable in a web page. We can use the PHP `echo` function for this. (Functions do all sorts of things, but more on that later)

```php
<?php $my_variable = 'I want to learn PHP'; ?>
<?php echo $my_variable; ?>
```
Because there is no HTML between these lines we can also write it like this.

```php
<?php
// This variable contains a string
$my_variable = 'I want to learn PHP';

echo $my_variable;
?>
```

This code will display `I want to learn PHP`.

PHP skips over lines that start with two forward slashes `//` (as if they don't exist). This is called a "PHP comment". Use them to a add explanations to your code. You can see a PHP comment in the code above.

To recap

* Variables hold values
* Variables can be reused throughout the code
* Values are assigned to variables with the "equals" sign
* A string is a series of characters inside quotes
* PHP comments start with two forward slashes
* PHP comments are not displayed