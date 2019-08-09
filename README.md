# Intro to Arrays

## Learning Goals
+ Use an array to store lists of elements
+ Use Ruby's %w[] literal to create an array
+ Split a String into an Array of words
+ Explain why you would want to store a list of data
+ Identify the first element of an array by index
+ Identify the first element of an array using `.first`
+ Identify some common array elements such as first, last, length, size, and include?
+ Use the shovel `<<` operator to add elements to an array
+ Use the pop method to remove the last element from an Array
+ Use the shift method to add an element to the front of an array

## Outline
+ Start with a problem - write a program that stores a bunch of names of people
+ This would be really tough:
  ```ruby
  name1 = "Katherine"
  name2 = "Dorothy"
  name3 = "Mary"
  ```
+ Because we don't know how many names we have. This will be really tricky to expand upon.
+ Instead, it would make more sense to make like a lists
+ Make an empty array - explain this is like a muffin tin. It's one thing, with potentially many other things inside of it
+ Unlike a muffin tin, can grow to be as big as it needs to be - no limit in Ruby
+ Demo creating an array called names
+ Demo adding an element, removing an element
+ Access by index - explain to count starting from zero
  + This is just how computers work - you get used to it
+ Demo pop, shift, unshift, and length/size
  + Ruby is helping you out by having length and size and count
+ Maybe, if there's time, write a quick program that asks for names to add to the array.
  + Each time name is added, print the first and last element and how many total there are
