# Learn the Basics of PHP

PHP is a popular programming language that is especially used for web development.

In this tutorial you learn the basic concepts of the PHP language and its terminology. It's assumed the reader has little to no knowledge of PHP or any other programming languages.

This tutorial has 5 chapters

* [Variables](https://keesiemeijer.github.io/php-basics-tutorial/variables)
* [Strings](https://keesiemeijer.github.io/php-basics-tutorial/strings)
* [Arrays](https://keesiemeijer.github.io/php-basics-tutorial/arrays)
* Loops
* Functions

## Introduction

A PHP file contains PHP tags and has the file extension `.php`. When PHP reads a PHP file, it searches for opening and closing PHP tags `<?php` and `?>`. This tells PHP the text inside the tags is actual PHP code. The great thing about PHP files is that they can contain HTML (and other languages) as well. 

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

---

<div CLASS="navigation">Next chapter: [Variables](https://keesiemeijer.github.io/php-basics-tutorial/variables)</div> 
