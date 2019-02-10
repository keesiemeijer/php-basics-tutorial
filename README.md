# Learn PHP basics in 15 minutes

PHP is a popular programming language that is especially used for web development.

In this tutorial you learn the basic concepts of the PHP language and its commonly used terminology. It's assumed the reader has little to no knowledge of PHP or any other programming languages. If you're just starting out with PHP this tutorial can help you with preventing errors, or finding in depth information about PHP more quickly (because you know the lingo).

## First things first

A PHP file contains PHP tags and has the file extension `.php`. When PHP reads a PHP file, it searches for opening and closing PHP tags `<?php` and `?>`. This tells PHP the text inside the tags is actual PHP code. The great thing about PHP files is that they can contain HTML (or other languages) as well. 

Here is a simple example of a web page with some HTML and PHP code.

```php
<html>
	<body>
		<p><?php echo 'Welcome to my web page'; ?></p>
	</body>
</html>
```

As you can see, the PHP code started and ended with the opening and closing PHP tags `<?php` and `?>`. If the file only contains PHP code you can just use the opening `<?php` PHP tag at the top of the file and leave the closing PHP tag `?>` altogether.

**Note**: PHP requires a semicolon (`;`) at the end of each PHP statement. If it's missing PHP will give you an error and stops processing the rest of the file. You can see the ending semicolon in the code above.

To recap:
* PHP files have a `.php` file extention
* PHP files can contain PHP and HTML
* PHP code needs to be inside opening and closing PHP tags.
* You only need the opening PHP tag if the file contains only PHP code
* A semicolon is needed after each PHP statement
* PHP stops working if there's an error

## Editing PHP Files
(Todo)

## Variables.

Let's start with a thing called "variables". In computer programming, a variable can hold a value. Variables in PHP start with a dollar sign `$` followed by the name of the variable. After declaring a variable it can be reused throughout the code. 

```php
<?php $my_variable = 'I want to learn PHP'; ?>
```

As you can see, the `$my_variable` variable has a value of `I want to learn PHP`. 

In PHP a "string" is a series of characters inside quotes. With this information we can say "The `$my_variable` variable contains a string". More about strings later.

Let's say we wanted to display the value of the variable in a web page. We can use the PHP `echo` function for this. (Functions do all sorts of things, but more on that later)

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

PHP skips over lines that start with two forward slashes (as if they don't exist). This is called a "PHP comment". Use them to a add readable explanations to your code. You can see a PHP comment in the code above.

To recap

* Variables hold values
* Variables can be reused throughout the code
* A string is a series of characters inside quotes
* PHP comments start with two forward slashes
* PHP comments are not displayed

## Strings.
As we have already learned, a string is a series of characters inside single or double quotes.

```php
$single_quoted_string = 'Hello';
$double_quoted_string = "Hello";
```

The values of these variables are exactly the same.

### Adding Strings Together
You can add strings together by separating them with a dot. We call this "string concatenation" (strange word indeed).

```php
$concatenated = 'Add a string' . ' to ' . 'another string';
```

The value of the `$concatenated` variable is now `Add a string to another string`. We can do exactly the same by assigning them with the concatenating assignment operator `.=`.

```php
$another_string = 'another_string';

$concatenated = 'Add a string';
$concatenated .= ' to ';
$concatenated .= $another_string;
```
The value of the `$concatenated` variable is `Add a string to another string`.

### Quotes Inside Strings
You need to be aware that you can't use the same type of quote inside a string. The following will get you an error.

```php
$single_quoted = 'Don't use single quotes in a single quoted string';
$double_quoted = "This "string" contains errors";
```

Using single quotes in a double quoted string or vice versa is totally fine.

```php
$single_quoted = 'This "is" fine';
$double_quoted = "This 'is' fine";
```

Or use concatenation.

```php
$concatenated  = 'This' . " 'is' " . 'fine, but less readable';
```

Another trick is by adding a backslash before the quotes `\"`. We call this "escaping". Escaping special characters with a backslash can only be done in double quoted strings.

```php
$double_quoted = "This \"is\" fine";
echo $double_quoted.
```
This code will display `This "is" fine` (without the backslashes). It doesn't produce errors because the quotes are escaped.

The caracters `\` and `$` in double quoted strings need escaping as well, because they have a special meaning.

```php
echo "this is a quote \", this is a backslash \\ and this is a dollar sign \$"
```
This code will display `this is a quote ", this is a backslash \ and this is a dollar sign $`

### Variables inside strings
Double quoted strings allow you to insert variables inside of them. The variable will be (what we call) "expanded" inside the string.

```php
$my_variable = 'I want to learn PHP';
echo "Hello, {$first_string}";
```

This will display `Hello, I want to learn PHP`.
If it was a single quoted string it would still display `Hello, {$first_string}`.

The curly brackets `{}` are optional (and also not displayed). But it's used to tell PHP "I am a variable that should be expanded".

**Note**: It's important to know that the value of the expanded variable should be a string.

To recap

* A string is a series of characters inside single or double quotes
* You can add strings together with concatenation (separating them with a dot)
* We can also do this with the concatenating assignment operator `.=`
* The wrong type of quote in a string can cause errors
* You can escape quotes and special characters with a backslash inside a double quoted string.
* Variables can be inserted in a double quoted string
* The value of the expanded variable should be a string

## Arrays
Arrays are variables that allow us to store more than one value in a single variable. It takes any number of comma-separated `key` => `value` pairs as arguments. Let me explain what this means.

This is an array with 3 `values` ( dog, cat and rabbit ) 

```php
$animals = array( 'dog', 'cat', 'rabbit' );
```

Because we didn't provide any `keys` in this array PHP sees it like this.
```php
array(
	0 => 'dog',
	1 => 'cat',
	2 => 'rabbit',
);
```

It adds the keys 0, 1 and 2 for us. This kind of array is called a "numerical" or "indexed" array because all the keys are numbers.

**Note**: It's very common in programming languages to start counting from 0.

We can use the keys to get a single value out from the array.

```php
$animals = array( 'dog', 'cat', 'rabbit' );
echo $animals[0];
```

This code will display `dog`.

By adding empty "square brackets" `[]` after the variable you can add a new value to the array.
```php
$animals = array( 'dog', 'cat', 'rabbit' );
$animals[] = 'chicken';
```

This is how PHP sees the array with the added `chicken` value.
```php
array(
	0 => 'dog',
	1 => 'cat',
	2 => 'rabbit',
	3 => 'chicken',
);
```
As you can see, it was added at the end.

(Todo) Associative arrays — An array where each key has its own specific value.
(Todo) Multidimensional arrays — An array containing one or more arrays within itself.

## Loops
(Todo)

## Functions
(Todo)
