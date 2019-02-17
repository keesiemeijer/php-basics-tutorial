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

As you can see, the `$my_variable` variable has a value of `I want to learn PHP`. We assigned this value to the variable with the equals sign `=`

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

PHP skips over lines that start with two forward slashes `//` (as if they don't exist). This is called a "PHP comment". Use them to a add explanations to your code. You can see a PHP comment in the code above.

To recap

* Variables hold values
* Variables can be reused throughout the code
* A string is a series of characters inside quotes
* PHP comments start with two forward slashes
* PHP comments are not displayed

## Strings.
As we have already learned, a string is a series of characters inside single `'` or double `"` quotes.

* A string with single quotes is called a `single quoted string`.
* A string with double quotes is called a `double quoted string`.

**Note**: The PHP opening and closing tags are left out in all code examples below. Assume the code is inside PHP tags `<?php  ?>`.

```php
$single_quoted_string = 'Hello';
$double_quoted_string = "Hello";
```

The values of these variables are exactly the same (`Hello`).

### Adding Strings Together
You can add strings together by separating them with a dot. We call this "string concatenation" (strange word indeed).

```php
$concatenated = 'Add a string' . ' to ' . 'another string';

echo $concatenated;
```

This code will display `Add a string to another string`.

We can do exactly the same by assigning them with the concatenating assignment operator `.=`

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
$single_quoted = 'Don't use single quotes in a single quoted string';
$double_quoted = "Don't use double "quotes" in a double quoted string";
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
echo "this is a quote \", this is a backslash \\ and this is a dollar sign \$";
```
This code will display `this is a quote ", this is a backslash \ and this is a dollar sign $`

### Variables inside strings
Double quoted strings allow you to insert variables inside of them. The variable will be (what we call) "expanded" inside the string.

```php
$my_variable = 'I want to learn PHP';
echo "Hello, {$my_variable}";
```

This code will display `Hello, I want to learn PHP`.
If it was a single quoted string it would still display `Hello, {$first_string}`.

The curly brackets `{}` are optional (and also not displayed). It tells PHP "This is a variable that should be expanded". I reccomend to always use them.

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
Arrays allow us to store more than one value in a single variable.

Array elements consist of `key` => `value` pairs separated by commas. Let me explain what this means.

This is an array with 3 string `values` dog, cat and rabbit, separated by commas.

```php
$animals = array( 'dog', 'cat', 'rabbit' );
```

We didn't add any array `keys` in this array. This is allowed because PHP will see it like this.

```php
array(
	0 => 'dog',
	1 => 'cat',
	2 => 'rabbit',
);
```

PHP adds the array keys 0, 1 and 2 for us (how nice!). 

The first array `element` of the `$animals` variable (above) has array `key` "0" with `value` "dog".

**Note**: Most programming languages start counting from 0.

* `Array keys` can either be (whole) numbers (starting from zero), or strings. 
* `Array values` can be of any type. There are many types of values. You already know "string", "number", and now "array". More value types are explained later.

**Note**: In PHP (and in math) we call whole numbers (without any decimal part) "integers".

Arrays with no values (elements) are also allowed. We call this an "empty array".

```php
$empty_array = array();
```

Arrays with **only** numbered keys are called "numerical" or "indexed" arrays 

#### Adding Values to Numerical Arrays
By adding empty "square brackets" `[]` after the variable you can add a new value to the array.

```php
$animals = array( 'dog', 'cat', 'rabbit' );

// Adding a value with empty square brackets
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
As you can see, it was added at the end. We can now say the last array `element` has array `key` "3" with `value` "chicken".

#### Accessing Values from Numerical Arrays

Use an existing array key inside the square brackets to access a value from a numerical array. 

```php
$animals = array( 'dog', 'cat', 'rabbit' );

// Getting the first value from the array.
$first_value = $animals[0];

echo "The first array value is {$first_value}";
```

This will display `The first array value is dog`. Remember, PHP sees arrays without array keys as an array with numbered keys (starting from zero).

#### Using Your Own Array Keys

As we've leared array keys can be integers or strings. Let's see how an array with string array keys looks like.

```php
$colors = array( 
	'grass' => 'green',
	'sky'   => 'blue',
);
```
The first array `element` has array `key` "grass" with `value` "green".

If **all or one** array key is a string we call it an  "associative array".

#### Adding Values to Associative Arrays

Use a unique array key inside square brackets to add a new value to the array.

```php
$colors = array( 
	'grass' => 'green',
	'sky'   => 'blue',
);

// Adding a value to the (new) 'firetruck' key
$colors['firetruck'] = 'red';
```

This is the value of the `$colors` variable after adding a value for the `firetruck` array key

```php
array( 
	'grass'     => 'green',
	'sky'       => 'blue',
	'firetruck' => 'red',
);
```

You can see it was added.
#### Accessing Values from Associative Arrays

Use an existing array key inside square brackets to access a value from an associative array.

```php
$colors = array( 
	'grass' => 'green',
	'sky'   => 'blue',
);

// Getting the value for the 'sky' array key.
$sky_color = $colors['sky'];

echo "The sky is {$sky_color}";
```

This code will display `the sky is blue`

#### Updating Array Values.
Use an existing array key inside square brackets to update array values.

```php
$colors = array( 
	'grass' => 'green',
	'sky'   => 'blue',
);

// Updating the sky array key value
$colors['sky'] = 'gray';

echo "The sky is {$colors['sky']}";
```

This code will display `the sky is gray`

#### Arrays Containing Arrays
Array keys can also have arrays as their value. Let's see how that looks like.

```php
$animals = array(
	'dog' => array(
		'name' => 'Max',
		'age'  => 3,
	),
	'cat' => array(
		'name' => 'Lucy',
		'age'  => 8,
	),
);
```

Arrays containing other arrays are called "multidimensional" arrays. The arrays inside an array are called "nested" arrays.

#### Adding Values to a Nested Array
Use an existing array key inside square brackets to target the nested array (you want to update). Add square brackets with a unique new key right after it to add a value. 


```php
$animals = array(
	'dog' => array(
		'name' => 'Max',
		'age'  => 3,
	),
	'cat' => array(
		'name' => 'Lucy',
		'age'  => 8,
	),
);
 
// Update the "dog" array with a new array element.
$animals['dog']['toy'] = 'tennisball';
```

This is the value of the `$animals` varable after updating.

```php
array(
	'dog' => array(
		'name' => 'Max',
		'age'  => 3,
		'toy'  => 'tennisbal',
	),
	'cat' => array(
		'name' => 'Lucy',
		'age'  => 8,
	),
);
```
As you can see the new array key "toy" with the value "tennisball" is added to the "dog" array.

#### Accessing Values from a Multidimensional Array
(Todo)

## Loops
(Todo)

## Functions
(Todo)
