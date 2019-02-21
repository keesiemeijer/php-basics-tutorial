# Learn the Basics of PHP

PHP is a popular programming language that is especially used for web development.

In this tutorial you learn the basic concepts of the PHP language and its terminology. It's assumed the reader has little to no knowledge of PHP (or other programming languages). It doesn't go too in depth into the PHP language itself. It's a starting point for people just starting out in the world of programming. The chapters are kept small and to the point.

It's recommended you go through the chapters in sequence. Each chapter uses information mentioned in the former chapters.

1. [Variables](https://keesiemeijer.github.io/php-basics-tutorial/variables)
2. [Strings](https://keesiemeijer.github.io/php-basics-tutorial/strings)
3. [Arrays](https://keesiemeijer.github.io/php-basics-tutorial/arrays)
4. Loops
5. Functions

## Introduction

PHP files are nothing more than simple text files with the file extension `.php`. When PHP reads a PHP file, it searches for opening and closing PHP tags `<?php` and `?>`. This tells PHP the text inside the tags is actual PHP code. The great thing about PHP files is that they can contain HTML (and other programming languages) as well. 

Here is an example of the contents of a PHP file for a web page.

```php
<!DOCTYPE html>
<html>
    <head>
        <title>My first web page</title>
    </head>
    <body>
        <p><?php echo 'Welcome to my web page'; ?></p>
    </body>
</html>
```

As you can see, it contains PHP and HTML code. the PHP code started and ended with the opening and closing PHP tags `<?php` and `?>`. If the file only contains PHP code you can just use the opening `<?php` PHP tag at the top of the file and leave the closing PHP tag `?>` altogether.

**Note**: PHP requires a semicolon (`;`) at the end of each PHP statement. If it's missing PHP will give you an error. It also stops with processing the rest of the code in the file. You can see an ending semicolon in the code above.

Errors are bound to happen, even to the most experienced developers. Don't worry about it. In this tutorial many common errors are explained. 

To recap:

* PHP files have a `.php` file extension
* PHP files can contain PHP and HTML
* PHP code needs to be inside opening and closing PHP tags.
* You only need the opening PHP tag if the file contains only PHP code
* A semicolon is needed after each PHP statement
* PHP stops working if there's an error
* Errors are bound to happen

## Editing PHP Files
(Todo)

---

<nav> 
    Next chapter: <a href="https://keesiemeijer.github.io/php-basics-tutorial/variables">Variables</a>
</nav> 
