## PHP Console
This is a small script that I wrote to make PHP debugging a little easier. I made it because my app was dealing with a lot of redirects, and I wanted to log information without it being erased after the redirect.

Here's a [video](http://www.screenr.com/uUj) that explains how to use it.

Everything is stored in a text file that gets created in the same directory as `console.php`.

## Usage
The first thing to do is make sure `console.php` is executable. And then run it in Terminal.

    chmod +x console.php
    ./console.php
    
By default `console.php` will reload the text file every 5 seconds. But you can change the time like this

    ./console.php delay=1
    
Then from your file include `console.class.php` and add logs with the following syntax.

```php
<?php
    Console::log('This will get added!');

    Console::log(array('This will be printed with print_r'));
?>
```
    
## Configuration
The console class has two variables that can be changed. The first is for where `console.txt` is created. And the second is for the time format.

```php
<?php
    // needs to point to the location of console.php
    Console::$filename = '../console.txt'; 

    Console::$time_format = 'F j, Y @ h:i:sa'; // default
?>
```