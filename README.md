# Intro to Arrays

## Learning Goals
+ Use an array to store lists of elements
+ Use Ruby's %w() literal to create an array
+ Split a String into an Array of words
+ Explain why you would want to store a list of data
+ Identify the first element of an array by index
+ Identify the first element of an array using `.first`
+ Identify some common array elements such as first, last, length, size, and include?
+ Use the shovel `<<` operator to add elements to an array
+ Use the pop method to remove the last element from an Array
+ Use the shift method to add an element to the front of an array

## Lesson

<iframe width="100%" height="720" src="https://www.youtube.com/embed/OeuJxVytL4Xs?rel=0&showinfo=0" frameborder="0" allowfullscreen></iframe>

+ Hi folks, it's Ian from Flatiron School. In this video, we're going to learn about storing lists of data in Ruby using Arrays.
+ By the end of this video, you should be able to:
  + Explain why you would want to store a list of data
  + Identify some common array elements such as first, last, length, size, and include?
  + Identify the first element of an array
  + Use an array to store lists of elements
  + Use Ruby's %w() literal to create an array
  + Use the shovel `<<` operator to add elements to an array
  + Use the pop method to remove the last element from an Array
  + Use the shift method to add an element to the front of an array
+ So let's get started. Let's pretend for a moment that we want to write a program that stores a bunch of names.
+ How might we do that? Well, one way would be to use local variables. So if we had three names, we could do something like this:
  ```ruby
  name1 = "Katherine"
  name2 = "Dorothy"
  name3 = "Mary"
  ```
+ This works, but has a bunch of problems.
  + This does not scale well. So with only three names, we can read this okay. But what if we had hundred or thousands or names? That would be really tough to work with.
  + We'd have no real way to answer any questions about the list. So, who is the first name? Who is the fourth, or twentieth? How many names do we have total? How many names start with the letter "H"?
+ Because this data, right now, has no structure to it. So this would be much easier if we had some structure, and I could say, hey, give me like a single list of names.
+ One great way to do that is using an Array. Arrays are built into Ruby and also many other programming languages, and let us deal with lists of data.
+ I'm going to open up an IRB session here in my terminal, and then I'm going to create an empty array called  `names` using the bracket symbols like so.
  ```ruby
  names = []
  ```
+ So I've just created an empty array, and this is kind of like a container, or like a suitcase. It's one thing, with potentially many other things inside of it.
+ Unlike a container, or a real suitcase, this array can grow to be as big as it needs to be. I can keep adding items into it
+ So I've created an empty array. If I want to know how many items are in this array, I can use the `.length` method like so:
```ruby
names = []
names.length #=> 0
```
+ So that will tell me how many items are in this array, and that can be useful when you're working with data structures and you want to know how many items are in that structure.
+ Now that we've created this array, let's look at ways that we can use it to store data. We'll look at adding new items into the array, access items stored in the array, and removing items from the array. First, let's look at adding.
+ In Ruby, there are a couple of ways to add elements to the array. I like to use what's called the shovel operator. The shovel looks like to "less-than" signs next to each other. So it goes array_name shovel_operator whatever I'm shovelling.
```ruby
names = []
names.length #=> 0
names << "Katherine"
```
+ If we look at the array now, we can see that it has one item in it - the one we just added. If we check the length, that will return one.
```ruby
names = []
names.length #=> 0
names << "Katherine"
name #=> ["Katherine"]
names.length #=> 1
```
+ Fun fact - you can also use `.count` or `.size` to get the length - Ruby is trying to be as friendly as possible and let you almost kind of guess at how to do stuff.
+ Let's add a couple more names into our array.
```ruby
names << "Dorothy"
names << "Mary"
```
+ If we check out length here, we'll see that we have three elements now, great.
```ruby
names.length #=> 3
```
+ So let's look now at how to read data out of the array. So pretend that this array was created some place else and we don't know what's inside of it. Ruby gives us a couple of handy methods to check the first and last element of the array - any guesses as to how to get the first element out of an array?
+ If you guessed `.first` - you got it. Same goes for `.last`
```ruby
names.first #=> "Katherine"
names.last #=> "Mary"
```
+ So that works well for those. To access the other elements, we can use an index number. Each element in the array is given a number based on the position.
+ The first element has an index of 0, the second element has an index of 1, and so forth.
  + This is just how computers work - you get used to starting from 0 after a while. There's a book called Learn to Program by Chris Pine, and in that book he suggests getting practice by counting things in your every day life starting from 0.
+ We can use bracket notation to read elements out of the array by index number.
+ So names bracket zero will give us the first element, names bracket 1 the second, names bracket two the third, and so on.
```ruby
names[0] #=> "Katherine"
```
+ So, with only three elements this isn't too helpful, but we might do this if we needed to do a loop - you could set up a counter, and loop or iterate over the whole list of names.
```ruby
index = 0
while index < names.length
  puts names[index]
end
```
+ Now, if we want to remove an element from the end of the array, we can use the `.pop` method. `.pop` pulls the last element off the array.
```ruby
names.pop
names.length #=> 2
```
+ So that works well for taking things off the end of the array. What if we want to manipulate from the front of the array?
+ We can do that using the "shift" and "unshift" method. "shift" pulls off the front, while "unshift" adds to the front
```ruby
names.unshift("Tina")
names.length #=> 3
names[0] #=> "Tina"
names[1] #=> "Katherine"
```
+ Notice how, using unshift, each index shifts up by one. So "Katherine" is in the second position now, and "Tina" is in the first.
+ So again, this is a bit of a contrived example just to show you how you can manipulate arrays. In real life, if I wanted to create an array with these names in it, I can do so just when I create the array literal.
```ruby
names = ["Katherine", "Dorothy", "Mary"]
```
+ And that works totally fine. Arrays can hold any kind of values I want to as well - numbers, symbols, or other data structures. You can even mix the types of elements in the array, though generally it's easier to work with if everything has the same type.
+ One other little trick - if you are creating an array of strings, Ruby has a little short cut. I can use percent-w-parenthesis and just write the bare words I want to be in the array, and that will work exactly the same way.
```ruby
names = %w(Katherine Dorothy Mary)
```
+ That works as long as I want an array of strings that are all single words, so you may see that sometimes.
+ Now, there are a ton of useful array methods that we haven't covered yet - one is `.include?` Say I want to find out if a value is in a list, I can use the `.include?` method, and that will return true/false based on whether or not the value is in the array. So:
```ruby
names.include?("Katherine") #=> returns true
name.include?("Ian") #=> returns false
```
+ And there are many more useful methods. Feel free to browse the Ruby documentation to see more.
+ So that's it for this video. Just to recap:
  + We explained why you would want to store a list of data - to make our applications easier to maintain.
  + We identified some common array elements such as first, last, length, size, and include?
  + We identified the first element of an array, both by index and using .first
  + We use an array to store lists of elements
  + We used Ruby's %w() literal to create an array
  + We also used the shovel `<<` operator to add elements to an array
  + We used the pop method to remove the last element from an Array
  + And we used the shift method to add an element to the front of an array
+ Thanks so much for watching - happy programming!
