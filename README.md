# Learn PHP basics in 15 minutes

PHP is a popular programming language that is especially used for web development.

In this tutorial you learn the basic concepts of the PHP language and its terminology. It's assumed the reader has little to no knowledge of PHP or any other programming languages. If you're just starting out with PHP this tutorial can help you with preventing errors, or finding in depth information about PHP more quickly (because you know the lingo).

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

**Note**: PHP requires a semicolon (`;`) at the end of each PHP statement. If it's missing PHP will give you an error and stops with processing the rest of the code. You can see the ending semicolon in the code above.

To recap:
* PHP files have a `.php` file extension
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
As we have already learned, a string is a series of characters inside single `'` or double `"` quotes.

**Note**: The PHP opening and closing tags are left out in all code examples below. Assume the code is inside PHP tags (`<?php  ?>`).

```php
$single_quote_string = 'Hello';
$double_quote_string = "Hello";
```

The values of these variables are exactly the same (`Hello`).

### Adding Strings Together
You can add strings together by separating them with a dot. We call this "string concatenation" (strange word indeed).

```php
$concatenated = 'Add a string' . ' to ' . 'another string';

echo $concatenated;
```

This code will display `Add a string to another string`. We can do exactly the same by assigning them with the concatenating assignment operator `.=`

```php
$another_string = 'another_string';

$concatenated = 'Add a string';
$concatenated .= ' to ';
$concatenated .= $another_string;

echo $concatenated;
```
This code will also display `Add a string to another string`.

### Quotes Inside Strings
You need to be aware that you can't use the same type of quote inside a string. The following will get you an error.

```php
$single_quotes = 'Don't use single quotes in a single quote string';
$double_quotes = "Don't use double "quotes" in a double quote string";
```

Using single quotes in a double quote string or vice versa is totally fine.

```php
$single_quotes = 'This "is" fine';
$double_quotes = "This 'is' fine";
```

Or use concatenation.

```php
$concatenated  = 'This' . " 'is' " . 'fine, but less readable';
```

Another trick is by adding a backslash before quotes `\"`. We call this "escaping". Escaping special characters with a backslash can only be done in a double quote strings.

```php
$double_quotes = "This \"is\" fine";
echo $double_quotes.
```

This code will display `This "is" fine` (without the backslashes). It doesn't produce errors because the quotes are escaped.

The caracters `\` and `$` in double quote strings need escaping as well, because they have a special meaning.

```php
echo "this is a quote \", this is a backslash \\ and this is a dollar sign \$";
```
This code will display `this is a quote ", this is a backslash \ and this is a dollar sign $`

### Variables inside strings
Double quote strings allow you to insert variables inside of them. The variable will be (what we call) "expanded" inside the string.

```php
$my_variable = 'I want to learn PHP';
echo "Hello, {$my_variable}";
```

This code will display `Hello, I want to learn PHP`.
If this was in a single quote string it would still display `Hello, {$first_string}`.

The curly brackets `{}` are optional (and also not displayed). But it's used to tell PHP "I am a variable that should be expanded".

**Note**: It's important to know that the value of the expanded variable should be a string.

To recap

* A string is a series of characters inside single or double quotes
* You can add strings together with concatenation (separating them with a dot)
* We can also do this with the concatenating assignment operator `.=`
* The wrong type of quote in a string can cause errors
* You can escape quotes and special characters with a backslash inside a double quote string.
* Variables can be inserted in a double quote string
* The value of the expanded variable should be a string

## Arrays
Arrays are variables that allow us to store more than one value in a single variable. It takes any number of comma-separated `key` => `value` pairs as arguments. Let me explain what this means.

This is an array with 3 `values` ( dog, cat and rabbit ) 

```php
$animals = array( 'dog', 'cat', 'rabbit' );
```

Because we didn't add any `keys` in this array PHP sees it like this.

```php
array(
	0 => 'dog',
	1 => 'cat',
	2 => 'rabbit',
);
```

It adds the keys 0, 1 and 2 for us. This kind of array is called a "numerical" or "indexed" array because all the keys are all numbers.

**Note**: Most programming languages start counting from 0.

#### Adding Values to a Numerical Array
By adding empty "square brackets" `[]` after the variable you can add a new value to the array.

```php
$animals = array( 'dog', 'cat', 'rabbit' );

// Adding a value
$animals[] = 'chicken';
```

This is how PHP sees the `$animals` variable after adding the `chicken` value.

```php
array(
	0 => 'dog',
	1 => 'cat',
	2 => 'rabbit',
	3 => 'chicken',
);
```
As you can see, it was added at the end.

#### Accessing Values from a Numerical Array

By adding a key (number) inside the square brackets you can access a value from a numerical array. 

```php
$animals = array( 'dog', 'cat', 'rabbit' );

// Getting the first value
$first_value = $animals[0];
```

The value of the `$first_value` variable is `dog`.

#### Using Your Own Array Keys

The numerical array only has numbered keys, but you can also create arrays with your own specific keys.

```php
$colors = array( 
	'grass' => 'green',
	'sky'   => 'blue',
);
```

This is called an "Associative array". It's an array where each key has its own specific value.

#### Adding Values to an Associative Array

By adding a specific key (string) inside the square brackets you can add a new value to the array.

```php
$colors = array( 
	'grass' => 'green',
	'sky'   => 'blue',
);

// Adding a value for the 'firetruck' key
$colors['firetruck'] = 'red';
```

This is the value of the `$colors` variable after adding a value for the `firetruck` key

```php
array( 
	'grass'     => 'green',
	'sky'       => 'blue',
	'firetruck' => 'red',
);
```
#### Accessing Values from a Associative Array

By adding a key (string) inside the square brackets you can access a value from a associative array.

```php
$colors = array( 
	'grass' => 'green',
	'sky'   => 'blue',
);

echo 'The sky is ' . $colors['sky'];
```

This code will display `the sky is blue`

#### Updating Array Values.
(Todo)

(Todo) Multidimensional arrays — An array containing one or more arrays within itself.

## Loops
(Todo)

## Functions
(Todo)
