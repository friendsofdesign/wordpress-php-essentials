# Basics of PHP Syntax

All programming languages have structure and formats that they need to follow so that the instructions that developers write can be decoded into functionality by the codes engine. This structure and format is commonly referred to as Syntax. Just like languages have syntax, so do programming languages. The syntax dictates the correct way to write code so that it is understood. PHP syntax is similar to JavaScript in many respects however there are key differences. Anyone with JavaScript experience will be able to recognise the similarities. PHP syntax is fairly simple and some key points need to be taken into account when writing PHP code. Syntax not only applies to the language as a whole but to how different functions, statements and arguments are written within the code. This will become more clear as you learn PHP.

PHP can be intermingled or written in between HTML and still run correctly \(see figure 5.1\). Notice the page has HTML tags on it, this is because of the way PHP is able to work within and in cooperation with HTML. The page is a .php file, but the HTML is still correctly parsed \(decoded\).

**IMAGE**

_Figure 5.1_

PHP can also be written on it’s own in PHP specific files \(see figure 5.2\). Here is a pure .php page which has no HTML on it. Only the PHP code need to run the function.

**IMAGE**

_Figure 5.2_

Just like in HTML we need to tell the page what programming language we will be using. In HTML this started by defining the page “DOCTYPE”, similarly in PHP we start with a PHP declaration. Thus the web server will know when it needs to read PHP and when it needs to read HTML and parse them correctly to the client \(browser\).

## The Basics

Let’s investigate the PHP declaration tag. As mentioned above we need to tell the server we will be writing in PHP. So we need to declare this to the server.

```php
<?php
  //php code will go between these declaration tags
?>
```

The first tag \(`<?php`\) informs the server that PHP has started and the end tag \(`?>`\) informs the server that PHP has ended. This is useful to us as we can then declare many areas on a webpage to be PHP in between the HTML we are writing, to make our site dynamic and load data where and when we want to.

## Basic PHP & HTML

Below is very basic PHP page. It will normally contain HTML and PHP.

```php
<!DOCTYPE html>
<html>
  <body>
    <h1>My first PHP page</h1>

    <?php
      // Some basic PHP code
      echo "Hello World!";
    ?>
  </body>
</html>
```

Create a new file named `index.php` in your `phpbasics` folder. Open this file in your web editor and then copy the code above into the file and save it. Then run the page and see what happens.

> **IMPORTANT!**
>
> Remember to start up your Bitnami WAMP/MAMP stack application and check to see if MySQL and Apache are running on the Manage Servers tab. Then open your favourite web browser \(like Chrome or Firefox\) and enter into the address bar the following "[http://localhost:80/phpbasics](http://localhost:80/phpbasics)". Please note the port number after the word localhost may be different on your setup. You can check to see what your port number is on the Manage Servers tab of the Bitnami application in Configure settings menu.

## Comments

Developers use comments for many reason, to remind themselves and other developers of what functions or code does, any errors they are experiencing and can’t reproduce in code. Most commonly comments are put into code as part of good code standards and practices.

Comment code when you need to explain complex functionality or logic that may not be obvious in the code.

```php
<?php
  // This is a single-line comment

  # This is also a single-line comment

  /*
  This is a multiple-lines comment block
  that spans over multiple
  lines
  */

  // You can also use comments to leave out parts of a code line
  $x = 5 /* + 15 */ + 5;
  echo $x;
?>
```

## Case Sensitivity

PHP has particular rules about case sensitivity, in some cases it is important to be case sensitive in others it will be ignored and the code will run either way. However it is also good practice to follow a standard in your code. It doesn’t have to be the international standard \(although it is recommended\) but it must be clear to any other developer that works with the code that there are particular ways of writing different parts of the code. We follow the international standards and so you will be learning this by default and it is noticeable in the examples we provide.

In the code below all three of the echo commands will run irrelevant of case. This is because all keywords \(`if`, `else`, `while`, `echo`, etc.\), classes, functions, and user-defined functions arenotcase sensitive.

```php
<?php
  ECHO "Hello World! <br>";
  echo "Hello World! <br>";
  EcHo "Hello World! <br>";
?>
```

However in the example below you will see that only the first statement will display the value of the `$color` variable \(this is because `$color`, `$COLOR`, and `$coLOR` are treated as three different variables\).

```php
<?php
  $color = "red";
  echo "My car is " . $color . "<br>";
  echo "My house is " . $COLOR . "<br>";
  echo "My boat is " . $coLOR . "<br>";
?>
```

## Variables

In PHP, a variable starts with the $ sign, followed by the name of the variable. The $ sign indicates to the PHP engine that a variable is about to be declared. Below we are declaring a couple of different variables with different datatypes.

```php
<?php
 $wording = "Hello world!";
 $myNumber = 5;
 $mySecondNumber = 10.5;
?>
```

As you can see we have declared three variables with different datatypes. The first is a string value of `"Hello World!"`, the second is an integer\(whole number\) and third is a float\(number with decimals\).

> **IMPORTANT!**
>
> Unlike other programming languages, PHP has no command for declaring a variable. It is created the moment you first assign a **value** to it.

A variable can have a short name \(like x and y\) or a more descriptive name \(age, carname, total\_volume\).

Rules for PHP variables:

* A variable starts with the `$` sign, followed by the name of the variable.
* A variable name must start with a letter or the underscore character.
* A variable name cannot start with a number.
* A variable name can only contain alphanumeric characters and underscores \(A-z, 0-9, and \_ \).
* Variable names are case-sensitive \(`$age` and `$AGE` are two different variables\).

## Output Variables & Data

Once we assign a value to a variable we can output this to the webpage. The PHPechostatement is often used to output the variable data.

```php
<?php
  $wording = "PHP";
  // Place the variable in the string we want to output
  echo "I love $wording!";
?>
```

The code example below will do the same as the code above however we are using the “dot syntax” to join the variable in the string. In other words we are using a full stop or dot to bind one piece of code with the string and then again bind string to the end of the variable.

```php
<?php
  $wording = "PHP";
  echo "I love " . $wording . "!";
?>
```

The example below is equivalent to a basic algebraic expressions in maths.

```php
<?php
  $x = 5;
  $y = 4;
  echo $x + $y;
?>
```

PHP is a **loosely typed language** and in the previous examples we did not have to declare to PHP what type of data the variable would hold. PHP will automatically try convert the variable to the correct data type, based on the value of the data assigned to the variable. This is different for other languages like C, C++ and Java, where the programmer must declare the name and type of the variable. It is thus important to keep in mind the data type you assign to variables.

## Variable Scope

Scope refers to where a variable can be used or referenced within the script. Scope changes according to where the variable is declared. There are three different types of scope in PHP.

* **Local** - A variable declared within a function and can only be referenced within that specific function.
* **Global** - A variable declared outside any functions.
* Static

### Global Scope

A variable declared outside a function has a **Global Scope** and can only be accessed outside a function. Like the example below:

```php
<?php
  // Global scope
  $globalVariable = 5;

  function myVariableTest() {
    // Using $globalVariable inside this function will generate an error
    echo "<p>Variable globalVariable inside function is: $globalVariable</p>";
  }

  myVariableTest();

  echo "<p>Variable globalVariable outside function is: $globalVariable</p>";
?>
```

Variables declared within a function has aLocal Scopeand can only be accessed within that function. See example below:

```php
<?php
  function myVariableTest() {
    // Local scope
    $globalVariable = 5;
    echo "<p>Variable globalVariable inside function is: $globalVariable</p>";
  }

  myVariableTest();

  // Using $globalVariable outside this function will generate an error
  echo "<p>Variable globalVariable outside function is: $globalVariable</p>";
?>
```

### Global Keyword

A global variable can be accessed from within a function when using the Global Keyword. This allows PHP functions to look outside of their own scope and search for variables with global scope.

```php
<?php
  $workdays = 5;
  $weeks = 10;

  function calculateWorkingDays() {
    // Tell the function to look for global variables
    global $workdays, $weeks;
    $totalWorkDays = $workdays * $weeks;
  }

  calculateWorkingDays();

  // Outputs 50
  echo $totalWorkDays;
?>
```

### Static Keyword

PHP will delete all of the variables once a function is completed or executed Sometimes we want a local variable to remain as we will be using it again in another function later. In this case we need to ensure PHP knows it is a static variable and not to delete after the initial function runs.

```php
<?php
  function staticTest() {
    static $staticVar = 0;
    echo $staticVar;
    $staticVar++;
  }

  // Outputs 1
  staticTest();
  // Outputs 2
  staticTest();
  // Outputs 3
  staticTest();
?>
```

## Echo and Print Statements

We have been using echo and print already in the examples above. And you may already have figured out what it does. Echo and Print allow us to write information or data to the PHP webpage.

```php
<?php
  // Outputs Hello! to the browser
  echo "Hello!";
?>
```

This will send the output Hello! to the browser. You can also output multiple “strings” or values.

```php
<?php
  echo "Hello!";
  echo "How are you?";
?>
```

Echo also allows us to output HTML along with variable and strings.

```php
<?php
  echo "<h2>Products</h2>";

  // Variable $school with string value
  $school = "Friends of Design";
  echo "You should study at $school";
?>
```

The differences between echo and print are very little, echo for example has no “return” value while print has a return value of “1”, so it can be used in expressions. Echo can take multiple parameters while print can take one argument. echo is marginally faster than print.

```php
<?php
  print "Hello, there";
?>
```

## PHP Data Types

PHP accepts a number of different data types that we can work with to develop our websites and applications, Each data type available can be used in conjunction with the code to produce the in functions we need. Consider compound interest, if we were working on a PHP app for a banking system, we may be asked to calculate compound interest. We would need to use the correct data type to ensure the amounts are correct in the daily interest calculations. For this a numbers with decimals would be most appropriate.

Data types we can use in PHP are as follows:

* String
* Integers \(Whole Numbers\)
* Float \(Decimal Numbers\)
* Boolean
* Array
* Objects
* Null
* Resource

### String

Any symbol or value contained within a “quotation” is considered to be a string. An integer refers to a positive or negative whole number \(no decimal points\). It must contain at least one digit i.e. 2. It cannot contain any commas or blanks. We have already used a number of string values in our examples see if you can identify them.

### Integers

An integer is a whole number that can be either positive or negative, and can range from -2,147,483,648 and 2,147,483,647. They must be at least one digit, and can be specified in three formats decimal \(10-based\), hexadecimal \(16-based - prefixed with 0x\) or octal \(8-based - prefixed with 0\). We have also used many integer data types in the previous examples. We are certain you can identify them by now.

### Float

A float or floating point number is a number value that has decimals or is in an exponential form like 

```php
<?php
  $floatNumber = 15.859;
  // The var_dump function allows us to output the value of the variable
  var_dump($floatNumber);
?>
```

### Boolean

PHP can also accept Booleans, a boolean is a true or false value, and these values can be stored within variables. These values are considered “states”, a state of “false” or “true”. Used to test conditional statements.

```php
<?php
  $truth = true;
  $lie = false;
?>
```

### Arrays

An array is basically at it’s heart a list object. It can contain multiple values and be stored in a variable. By their nature variables cannot store more than one piece of information or value, but an array object can store multiple and then be stored in a variable to be manipulated later. The syntax for an array is as follows.

> **IMPORTANT**
>
> Remember in programming we always start counting at 0 when doing arrays and lists.

There are three main types of arrays.

* **Indexed arrays** - Arrays with a numeric index
* **Associative arrays** - Arrays with named index keys
* **Multidimensional arrays** - Arrays containing one or more arrays

```php
<?php
  $cars = array('BMW', 'Mercedes', 'Bentley');
  // Echo the index (item number) in the array
  echo $cars[0];
?>
```

Below we have defined an array using the “Index Key” syntax, which is an identifier for the value in the array. With an index we can identify specific values in the array more easily and give them a common human readable name.

```php
<?php
  $cars = [
    "BMW" => "M3",
    "Mercedes" => "S Class",
    "Bentley" => "Continental"
  ];

  // Echo the index key - identifier of the item value
  echo $cars['Mercedes'];
```

Arrays can also be sorted and arranged differently. There are multitude of functions to manage arrays, you can find out more here about sorting arrays.

[http://www.w3schools.com/php/php\_arrays\_sort.asp](http://www.w3schools.com/php/php_arrays_sort.asp) or [http://php.net/manual/en/language.types.array.php](http://php.net/manual/en/language.types.array.php)

### Object

A PHP object is a special data type which allows us to store data and information which will help us interpret and process the data later. PHP objects need to be declared explicitly, meaning we must take special precaution to inform PHP we are using an object. Objects are more complex than most data types and so we must follow the syntax of how to create an object. First we create a class for the object and then define the function to call the object when we need it in code.

```php
<?php
  // Create the class
  class Shop {
    // Create the function
    function Shop() {
      $this->model = "Woolworths";
    }
  }

  // Define the object
  $myStore = new Shop();
  // Shows us the object properties
  echo $myStore->model;
?>
```

We will need to follow this syntax consistently to create object. More will be explored on objects later.

### Null Value

A null value can only have one value, which is null. It is a variable with no data assigned to it specifically, and variables can also be set to null by removing their value. Nulls can be used to ascertain whether a variable has been assigned a value at some point in the code. If we test the variable value and get back a null we can see that it has not yet received the value we intended.

```php
<?php
  // Variable without assigning value therefore the value will be null
  $value;
  // Check the variable's value
  var_dump($value);

  // Echo line to separate values
  echo "<hr/>";

  // Change the variable's value from null to string
  $value = "Some string";
  // Echo the variable's value
  echo $value;
?>
```

### Resource

A PHP resource is another very special data type that is not technically a data type at all. It used to make calls to the database and used for storing external functions and references, those that may exist in other PHP files or API’s. This will be used for advanced functions and systems development. As we have limited time in the course we will not go into using resource, however you can read up about its use and syntax here at the official PHP Manual site.

[http://php.net/manual/en/language.types.resource.php](http://php.net/manual/en/language.types.resource.php)

