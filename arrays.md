## Arrays
In most programming languages, an array is a collection of elements. Arrays allow us to store more than one value in a single variable.

Here's how an array is described in PHP.

* An `array` has `elements` separated by commas
* An `array element` has a `key` and a `value`

Let me explain what this means.

This is an array with 3 array elements (dog, cat and rabbit).

```php
$animals = array( 'dog', 'cat', 'rabbit' );
```

This array has no array keys. PHP sees arrays without keys as if it has numbered array keys. In this example PHP sees it like this (with array keys 0, 1 and 2).

```php
$animals = array(
	0 => 'dog',
	1 => 'cat',
	2 => 'rabbit',
);
```

Arrays with **only** numbered keys are called `numerical arrays`. For convenience we don't have to add the keys for numerical arrays if we don't want to.

As you can see, the format for array elements in PHP is `key => value` with the `=>` part seperating the key from the value. It's also allowed to have a comma after the last element (see `2 => 'rabbit',`).

In PHP lingo we can now say "The first element of this array has array key `0` with the array value `dog`."

**Note**: Most programming languages start counting from 0.

Arrays with no elements are also allowed. We call this an "empty array".

```php
$empty_array = array();
```


#### Keys and Values 

* `Array keys` can either be (whole) numbers (starting from zero), or strings. 
* `Array values` can be of any type. You already know the types `string`, `number`, and now `array`. More value types are explained later.

**Note**: In PHP (and in math) we call whole numbers (without any decimal part) "integers".

#### Adding Values to Numerical Arrays
By adding empty "square brackets" `[]` after the array variable you can add a new value to it.

```php
$animals = array( 'dog', 'cat', 'rabbit' );

// Adding the 'chicken' value to the array
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
As you can see, it was added at the end. We can now say, "The last array element has array key `3` with array value `chicken`.

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

As we've leared array keys can be integers or strings. Let's see how an array with our own (string) array keys looks like.

```php
$colors = array( 
	'grass' => 'green',
	'sky'   => 'blue',
);
```
For this array we can say, "The first array element has array key `grass` with array value `green`".

If **all or one** array key is a string we call it an `associative array`.

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

You can see the `firetruck` key with value `red` was added to the array.
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

Arrays containing other arrays are called `multidimensional arrays`. The arrays inside a multidimensional array are called `nested arrays`.

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

This is the value of the `$animals` varable after updating it with the new `toy` key.

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
As you can see the new `toy` key with the value `tennisball` is added to the `dog` array.

#### Accessing Values from a Multidimensional Array
(Todo)

---

<nav>
  <ul>
    <li>Previous chapter: <a href="https://keesiemeijer.github.io/php-basics-tutorial/strings">Strings</a></li>
  </ul>
</nav>
