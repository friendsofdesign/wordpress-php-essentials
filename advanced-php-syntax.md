# Advanced  PHP  Syntax

## PHP String Functions

A string function is a predefined function that is already in existance within PHP and it can be used to change and manipulate string data types. We will be looking at two examples of string functions.

When you test this example below please notice that spaces are counted as characters.

```php
<?php
  // The string length function (strlen) will output 17
  echo strlen("How long is this?");
?>
```

Notice below the reverse string function will completely mirror/reverse the letters in the string, even the letters are swapped around.

```php
<?php
  // Outputs ?siht daer I naC
  echo strrev("Can I read this?");
?>
```

There are many more string functions, the full list of string functions can be viewed at w3schools. [http://www.w3schools.com/php/php\_ref\_string.asp](http://www.w3schools.com/php/php_ref_string.asp)

## PHP Constants

Constants are similar to variables however they cannot be changed. They are identifiers for simple value. They will not be altered or changed in the code at a later point. We must define constants using the “define\(\)” function using specific syntax.

```php
define(name, value, case-insensitive);
```

```php
<?php
  define("WELCOME", "Welcome to the Friends of Design PHP short course!");
  echo WELCOME;
?>
```

Notice that we don’t declare constants in the same manner as a variable and don’t use the “$” symbol before the namespace. We can also set constants to not be case-sensitive or be case-insensitive.

```php
<?php
  define("HIYA", "Hi there!" , true);
  echo hiya;
?>
```

Take a look at the example above, by setting the parameter of true can echo the constant “HIYA” as “hiya” without being case-sensitive and still return the string data. It is good practice to keep constants case-sensitive \(all caps\) as they are accustomed to seeing constants in that format.

## Operators

### Arithmetic Operators

PHP like all modern programming languages have a series of arithmetic operators to allow for calculations.

| Operator | Name | Example | Result |
| :--- | :--- | :--- | :--- |
| + | Addition | $x + $y | Sum of $x and $y |
| - | Subtraction | $x - $y | Difference of $x and $y |
| \* | Multiplication | $x \* $y | Product of $x and $y |
| / | Division | $x / $y | Quotient of $x and $y |
| % | Modulus | $x % $y | Remainder of $x divided by $y |
| \*\* | Exponentiation | $x \*\* $y | Result of raising $x to the $y'th power \(Introduced in PHP 5.6\) |

Operators allow us to add subtract numbers or data stored in variables.

```php
<?php
  $x = 5;
  $y = 7;
  $z = $x + $y;

  // Outputs the sum of the algebraic expression x + y = z
  echo "total " . $z;
  // Separating line
  echo "<hr>"; 
  // Alternative way of outputting the same expression
  echo "total " . ($x + $y);
?>
```

We can also use string concatenation, and bind stings and variable values. As seen in the last echo statement above. The “.” symbol allows us to bind variables together and create complex echo statements.

```php
<?php
  $txt1 = "Hello";
  $txt2 = $txt1 . " world!";
  // Outputs "Hello world!"
  echo $txt2;
?>
```

### Increment and Decrement Operators

These allow us to increment number values.

| Operator | Name | Description |
| :--- | :--- | :--- |
| ++$x | Pre-increment | Increments $x by one, then returns $x |
| $x++ | Post-increment | Returns $x, then increments $x by one |
| --$x | Pre-decrement | Decrements $x by one, then returns $x |
| $x-- | Post-decrement | Returns $x, then decrements $x by one |

```php
<?php
  $x = 10;
  // Outputs 11
  echo ++$x;
  echo "<hr>";
  $y = 2;
  // Outputs 1
  echo --$y;
?>
```

These incremental and decremental operators are useful for counting in code. For example using increment to count through many images stored on a server, each image file will be counted and when it’s counted as true \(it exists\) we add one to the total for each true value returned.

### Comparison Operators

PHP and all programming logic requires on logic to function correctly, being able to compare values allows developers to create complex logic responses. If a user has -R10 000 in their bank account and the bank wants to warn them that they have reached their limit. When we compare the limit value with the bank accounts current amount available, we can see if the user has reached the limit of -R10 000. If they have reached point we can warn them via a message or visual response.

| Operator | Name | Example | Result |
| :--- | :--- | :--- | :--- |
| == | Equal | $x == $y | Returns true if $x is equal to $y |
| === | Identical | $x === $y | Returns true if $x is equal to $y, and they are of the same type |
| != | Not equal | $x != $y | Returns true if $x is not equal to $y |
| &lt;&gt; | Not equal | $x &lt;&gt; $y | Returns true if $x is not equal to $y |
| !== | Not identical | $x !== $y | Returns true if $x is not equal to $y, or they are not of the same type |
| &gt; | Greater than | $x &gt; $y | Returns true if $x is greater than $y |
| &lt; | Less than | $x &lt; $y | Returns true if $x is less than $y |
| &gt;= | Greater than or equal to | $x &gt;= $y | Returns true if $x is greater than or equal to $y |
| &lt;= | Less than or equal to | $x &lt;= $y | Returns true if $x is less than or equal to $y |

```php
<?php
  $currentBalance = 4000.00;
  $balanceLimit = 5000.00;
  $warningMessage = '<span style="color:red;">You have reached your limit of R' . $balanceLimit . '</span><br>';

  // Echo message if limit is reached
  if($currentBalance == $balanceLimit) {
    echo $warningMessage;
  } else {
    echo "You have spent: R" . $currentBalance . "<br>" . '<span style="color:green">You have R' . ($balanceLimit - $currentBalance) . " credit remaining.</span>";
  }
?>
```

Give the above code a test and see what happens if you make the current balance less than the balance limit. You will notice we have intermingled CSS styles and arithmetic functions to change color and display the balances based on the conditions which are met. We can expand on this logic further using more complex logic.

### Logic Operators

We often will in some cases need to consider two or more values to make a condition true or false. Or we will need to execute a change or function based on one value or another. Logic operators allow us to achieve complex logic for such complex situations.

| Operator | Name | Example | Result |
| :--- | :--- | :--- | :--- |
| and | And | $x and $y | True if both $x and $y are true |
| or | Or | $x or $y | True if either $x or $y is true |
| xor | Xor | $x xor $y | True if either $x or $y is true, but not both |
| && | And | $x && $y | True if both $x and $y are true |
| \|\| | Or | $x \|\| $y | True if either $x or $y is true |
| ! | Not | !$x | True if $x is not true |

```php
<?php
  $productA = 450.00;
  $productB = 35.00;
  $productC = 15.00;
  $currentFunds = 480.00;

  if($productA < $currentFunds && $productB + $productC == $currentFunds - $productA) {
    echo 'You have R' . ($currentFunds - $productA) . ' remaining.' . '<br>';
    echo 'You can still afford a R' . $productC . ' voucher or a R' . $productB . ' voucher.';
  } else {
    echo 'You have: R' . ($currentFunds - $productA) . '<br> Not enough funds available.';
  }
?>
```

Try figure out for yourself what is happening in the logic. Test the logic by making the current funds in the example above equal to “500.00” and see how the code responds.

## Conditional Statements

There are number of conditional statements in PHP, as we have started illustrating in the previous section, conditional statements help us structure logic and responses to changes in the data. The most common conditional statement, used above, is the `if` statement. If statements help us set the base condition of "if something like this happens" then "run this code".

### If Statements

The syntax for `if` statements is quite specific. Remember to close brackets and end code arguments with `;` symbols.

```php
if(condition)   {
  // Code executed when the condition is met or true
}
```

In the example below we will check to see `if` the value equals 5. Then we will run the code to show the value.

```php
<?php
  $value = 5;

  if($value == 5) {
    echo 'The value is equal';
  }
?>
```

Try changing the value to 4 or 3 and see what happens next.

### If Else Statements

"If Else" statements allow us to add a second option to the code, allowing our response to be more accurate or refined to the systems needs. The overall syntax stays the same however we append the `else` statement to the end of the `if` statement as shown below, and it doesn’t have a specific condition.

```php
<?php
  $value = 6;

  if($value == 5) {
    echo 'The value is equal';
  } else {
    // Adding the else statement to the end of the if statement completes the if else
    echo 'The value is not equal';
  }
?>
```

### If Elseif Else Statement

This is the third variation in the `if` statement structure. We may have more conditions in more complex systems that the user will need to match to get a result. We want to make sure the code gets a response, so we can add an "Elseif" statement between the `if` and `else` statements, in the same syntax as the `if` statement, allowing for a condition to be defined.

```php
<?php
  $value = 6;

  if($value == 5) {
    echo 'The value is equal';
  } else if($value < 5) {
    // Adding the else if statement to middle of the if statement
    echo 'The value is less than 5';
  } else {
    echo 'The value is greater than 5';
  }
?>
```

Take note that the final `else` statement only will run if the other conditions are false. If the other 2 are false, then the final else must be true. Process of elimination basically.

We can also use "Switch statements" in place of an "If statement", the effect is the same. Switch statements will test each condition to be true or false and when the correct condition is met, it will switch to the appropriate state or run the correct code. For more about "Switch Statements" check out this great example.

[http://www.w3schools.com/php/php\_switch.asp](http://www.w3schools.com/php/php_switch.asp)

## While Loops

The "While loop" is a special statement that like an "If Statement" will execute code when the condition is met or true. While loop will continue step through or increment over code as long as the condition remains true. Consider the following example.

```php
<?php
  $x = 1;
  while($x <= 5) {
    echo "The number is: $x <br>";
    $x++;
  }
?>
```

This code will keep checking to see if `$x` is less than or equal to 5. As long as the condition is true it will echo the number and then increment it by one. Once the value of `$x` is equal to 5 it will stop.

## For Loops

The "For loop" is a powerful but slow conditional statement, it is used to step over or go through an array \(list\) of items and apply the code that is specified to each in the array. This should only be used when you know how many times the code should run.

The "For loop" syntax is quite important and broken into the following structures.

```php
for (init counter; test counter; increment counter) { 
  // Code to be executed;
}
```

**Parameters of the For Loop:**

* **init counte**r: Initialize the loop counter value
* **test counter**: Evaluated for each loop iteration.
  * If it evaluates to TRUE, the loop continues.
  * If it evaluates to FALSE, the loop ends.
* **increment counter**: Increases the loop counter value

If you have a list of 7 numbers and want to display them you could do the following with a "For loop":

```php
<?php
  for ($x = 0; $x <= 7; $x++) {
    echo "The number is: $x <br>";
  }
?>
```

The parameters of the "For loop" set the instructions for the loop. First we tell it where to begin, in this case `$x = 0`, then we tell it how many times to loop 7 \(`$x <= 7`\), then we instruct the starting value to increment to the next number `$x++`. Like telling the code to go from 0 to 1, then to 2 etc.

## Foreach Loops

The "Foreach loop" is a special loop that allows the manipulation of arrays, "Foreach loops" only work with arrays. The allow for the step through the list of items in the array and the execution of the code for each item. Once again the syntax is very specific for this type of loop, as we must pass the correct parameters and instructions to the loop.

```php
foreach ($array as $value) {
  // Code to be executed
}
```

We define the the "foreach" statement and then the condition, where the array items become the value of the code executed in the loop. As in the example below.

```php
<?php
  // First create a simple array object
  $dogs = [
    'pitbull',
    'mastif',
    'spaniel',
    'fox terrier'
  ];

  $number = 0;
  // Then define the foreach loop to display each item in the array
  foreach($dogs as $breeds) {
    echo ++$number . ' ' . $breeds . '<br/>';
  }
?>
```

The code above we define the an array using the square bracket syntax - see arrays - and then we define a variable `$number` to act as our numbering system. Then we ask the create a "foreach loop" to step through all the list items, we then echo the number, a space, and the names of breeds, with a line break at the end to put each one on a new line.

## PHP Functions

There are many predefined PHP functions used in PHP to write the code of systems and websites. In fact there are too many to give an appropriate amount of time to each. For the whole list of functions available check out the following links.

The PHP Manual - [http://php.net/manual/en/language.functions.php](http://php.net/manual/en/language.functions.php) OverApi - [http://overapi.com/php](http://overapi.com/php)

Each provides a comprehensive list of all functions. It’s common for developers to keep links like this handy as despite years of working on PHP not everyone remembers each function 100%. However if we can’t find a function we can use or need to create a custom function, PHP allows us to do so. More often than not developers will create custom functions for their system or website.

Functions are the backbone of the system, they provide the logic structure to how the system will work and what will happen when.

### Function Syntax

The syntax looks as follows:

```php
function functionName() {
  // Code for function;
}
```

Using the keyword `function` we inform PHP we are about to define a function. We give our function a custom name or namespace, and then proceed to add the correct arguments to the function so that it can do what we want it to do. Functions can also accept parameters. Once this is defined we have a reusable block of code we can execute or call when we need to.

```php
<?php
  function myFirstFunction() {
    echo "This is my first custom PHP function!";
  }

  myFirstFunction();
?>
```

We now can call this function whenever we want to echo out the string we defined. This is very basic function but the core idea remains the same no matter the complexity of the logic. To make our functions more useful to use we can pass parameters through our function, allowing it to accept data based on the parameter. The function will then use the data defined in the parameter to fill in the blanks in the function as follows:

```php
<?php
  function fullname($firstname, $surname, $dob) {
    // Echo full name and date of birth in a single string
    echo $firstname . ' ' . $surname . ', born on ' . $dob . '<br>';
  }

  // Call the function multiple times with different data sets
  fullname('Andrew', 'Spies', '19/11/1984');
  fullname('John', 'Cleese', '27/10/1939');
  fullname('Stephen', 'Hawking', '08/01/1942');
?>
```

We can now use the function above to call the different sets of data as parameters. We can even pass variables as parameters should we need to.

```php
<?php
  function fullname($firstname, $surname, $dob) {
    // Echo full name and date of birth in a single string
    echo $firstname . ' ' . $surname . ', born on ' . $dob . '<br>';
  }

  $userFirstName = "Isaac";
  $userSurname = "Newton";
  $userDob = "04/01/1643";

  fullname($userFirstName, $userSurname, $userDob);
}
```

As you can see above we define the data in some variables describing the parameter positions we want them to take up. When the function runs the variable data is passed to the function parameters and the correct information is displayed.

## Working with HTML in PHP

PHP is able to add HTML elements to the page, and their are a number of ways to do this. This is often done to change the page based on a function. For example showing a DIV when an error occurs.

```php
<?php if(5 === 5) { ?>
  <h2 class="title">It’s Equal!</h2>
<?php } ?>
```

Here we are wrapping the PHP code around an HTML tag and breaking the PHP code into pieces as the HTML won’t render it, if it is between PHP tags. Thus we need to do the initial PHP code that will start process we are trying to create, then put down the HTML and then complete the PHP code. Give it a test!

Another way to write the code to get the same result is a follows.

```php
<?php
  if(5 === 5) {
    // Escape the inner pair of double quote marks
    echo "<h2 class=\"title\">It’s Equal!</h2>";
  }
?>
```

There are benefits and drawbacks to each method. It’s up to the developer to decide which standard works best in which situation. The second example can also be written with single quotes around the HTML and then the  symbols need not be used to escape the inner double quotes.

```php
<?php
  if(5 === 5) {
    // No need to escape any quote marks
    echo '<h2 class="title">It is Equal!</h2>';
} ?>
```

The code above is the same but no need for hard to read escapes which clutter the code.

