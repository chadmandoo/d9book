---
title: Utility
---

# Actions
![views](https://api.visitor.plantree.me/visitor-badge/pv?label=views&color=informational&namespace=d9book&key=utility.md)

## Overview

Drupal provides developers with a variety of utility functions that make it easier and more efficient to perform tasks that are either really common, tedious, or difficult. Utility functions help to reduce code duplication and should be used in place of one-off code whenever possible.

## Random 

The Drupal 10 Random Utility class is a collection of methods for generating random data. It can be useful in a variety of scenarios, such as generating dummy data for testing purposes, creating unique identifiers, or generating random strings. Examples below:

```php
use Drupal\Component\Utility\Random;
 
$random = new Random();

/**
* Generates a random string containing letters and numbers.
* name($length = null, $unique = FALSE)
*/
$name = $random->name(9);
echo $name; // outputs a random string with length of 9 characters

/**
* Generates a random string of ASCII characters of codes 32 to 126
* string($length, $unique = FALSE, $validator = NULL)
*/ 
$string = $random->string(8);
echo $string; // outputs a random lowercase string with length 8, such as "xptzfhkd"

/**
* Generate a string that looks like a word (letters only, alternating consonants and vowels)
* word($length = 10) - random word
*/
$word = $random->word(6);
echo $word; // outputs a random 6-letter word

/**
* Generates a string containing lowercase letters and numbers.
* machineName($length = 8, $unique = FALSE)
$machineName = $random->machineName(16);
echo $machineName; // Outputs a random machine-readable name

/**
* Generates sentences Latin words, often used as placeholder text.
* sentences($min_word_count = 3, $capitlize = FALSE)
*/
$sentences = $random->sentences(10);
echo $sentences; // Outputs a 10 word sentence

/**
* Create a placeholder image.
* image($destination, $min_resolution, $max_resolution)
*/
$image_path = $random->image('/tmp/test.jpg', '200x400', '300x600');
echo $image_path; // Outputs path for a placeholder image with dimensions random between 200x400 and 300x600 

/**
* Generates a random PHP object.
* object($count = 3) - random object
*/
$object = $random->object(4);
print_r($object); // Outputs a random object with 4 properties

/**
* Generate paragraphs separated by double new line.
* paragraphs($count = 3) - random paragraphs
$paragraphs = $random->paragraphs(5);
echo $paragraphs; // Outputs 5 random paragraphs utilizing the sentences method
```

## Reference

- [Utility classes and functions Drupal API](https://api.drupal.org/api/drupal/core%21core.api.php/group/utility/10)
