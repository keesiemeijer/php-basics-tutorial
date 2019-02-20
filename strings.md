# Strings

As you've seen already, a string is a series of characters inside single `'` or double `"` quotes.

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

Another trick is by adding a backslash before the quotes `\"`. In PHP this is called "escaping". 

```php
$single_quoted = 'This \'is\' fine';
$double_quoted = "This \"is\" fine";
echo $double_quoted.
```

This code will display `This "is" fine` (without the backslashes). It doesn't produce errors because the quotes are escaped.

### Variables inside strings
Double quoted strings allow you to insert variables inside of them. The variable will be (what we call) "expanded" inside the string.

```php
$my_variable = 'I want to learn PHP';
echo "Hello, {$my_variable}";
```

This code will display `Hello, I want to learn PHP`.
If it was a single quoted string it would still display `Hello, {$first_string}`.

The curly brackets `{}` are optional (and also not displayed). It tells PHP "This is a variable that should be expanded". I recommend to always use them. It can prevent errors in some situations. 

**Note**: It's important to know that the value of the expanded variable should be a string.

To recap

* A string is a series of characters inside single or double quotes
* You can add strings together with concatenation (separating them with a dot)
* We can also do this with the concatenating assignment operator `.=`
* The wrong type of quote in a string can cause errors
* You can escape quotes.
* Variables can be inserted in a double quoted string
* The value of the expanded variable should be a string
