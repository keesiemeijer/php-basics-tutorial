# Learn PHP basics in 15 minutes

PHP is a popular programming language that is especially used for web development.

In this tutorial you learn the essential basics of PHP and what terminology is used. This can be helpfull in preventing errors or looking up PHP related information on the web when you just start out. It's assumed the reader has little to no knowledge of PHP or other programming languages. 

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

As you can see, the PHP code started and ended with the opening and closing PHP tags `<?php` and `?>`. If the whole file is only PHP code you can just use the opening `<?php` PHP tag at the top of the file and leave the closing PHP tag `?>` altogether.

**Note**: PHP requires a semicolon (`;`) at the end of each PHP statement. It will result in errors if you leave it out. PHP stops working after errors. You can also see the ending semicolon in the code above.

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

PHP skips over lines if they start with two forward slashes (as if they don't exist). This is called a "PHP comment". Use them to a add readable explanations to your code. 

To recap

* Variables hold values
* Variables can be reused throughout the code
* A string is a series of characters inside quotes
* PHP comments start with two forward slashes
* PHP comments are not displayed

## Strings.
A string is a series of characters inside single or double quotes.

```php
$single_quoted_string = 'Hello';
$double_quoted_string = "Hello";
```

The values of these variables are exactly the same.

### Adding Strings Together
You can add strings together by separating them with a dot. We call this "string concatenation" (strange word indeed).

```php
$concatenated_string = 'Add a string' . ' to ' . 'another string';
```

The value of the `$concatenated_string` variable is now `Add a string to another string`. We can do exactly the same by assigning them with the concatenating assignment operator `.=`.

```php
$another_string = 'another_string';

$string = 'Add a string';
$string .= ' to ';
$string .= $another_string;
```
The value of the `$string` variable is `Add a string to another string`.

### Quotes Inside Strings
You need to be aware that you can't use the same type of quote inside a string. The following will get you an error.

```php
$single_quoted = 'Don't use single quotes in a single quoted string';
$double_quoted = "This "string" has errors";
```

Using single quotes in a double quoted string or vice versa is totally fine.

```php
$single_quoted = 'This "is" fine';
$double_quoted = "This 'is' fine";
```

Or you can use concatenation.

```php
$concatenated  = 'This' . " 'is' " . 'fine, but less readable';
```

Another trick is by adding a backslash before the quotes `\"`. We call this "escaping a quote in a string". Escaping special characters with a backslash can only be done in double quoted strings. The following has no errors and displays `This "is" fine` (without the backslashes).

```php
$double_quoted = "This \"is\" fine";
echo $double_quoted.
```

The caracters `\` and `$` in double quoted strings need escaping as well, because they have a special meaning.

```php
echo "this is a quote \", this is a backslash \\ and this is a dollar sign \$"
```
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
(Todo)

## Loops
(Todo)

## Functions
(Todo)
