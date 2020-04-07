## What is functional programming?
Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data .

## The first fundamental concept we learn when we want to understand functional programming is pure functions. But what does that really mean? What makes a function pure?
* So how do we know if a function is pure or not? Here is a very strict definition of purity:
* It returns the same result if given the same arguments (it is also referred as deterministic)
* It does not cause any observable side effects.

## Pure functions benefits
The code’s definitely easier to test. We don’t need to mock anything. So we can unit test pure functions with different contexts:
Given a parameter A → expect the function to return value B
Given a parameter C → expect the function to return value D.

## When data is immutable, its state cannot change after it’s created. If you want to change an immutable object, you can’t. Instead, you create a new object with the new value.
In Javascript we commonly use the for loop. This next for statement has some mutable variables.

## The idea of functions as first-class entities is that functions are also treated as values and used as data.

### Functions as first-class entities can:

* refer to it from constants and variables
* pass it as a parameter to other functions
* return it as result from other functions

The idea is to treat functions as values and pass functions like data. This way we can combine different functions to create new functions with new behavior.

### These functions have similar logic, but the difference is the operators functions. If we can treat functions as values and pass these as arguments, we can build a function that receives the operator function and use it inside our function. Let’s build it!.

## Higher-order functions

### When we talk about higher-order functions, we mean a function that either:

* takes one or more functions as arguments, or
* returns a function as its result

The doubleOperator function we implemented above is a higher-order function because it takes an operator function as an argument and uses it.

## Filter

Given a collection, we want to filter by an attribute. The filter function expects a true or false value to determine if the element should or should not be included in the result collection. Basically, if the callback expression is true, the filter function will include the element in the result collection. Otherwise, it will not.

A simple example is when we have a collection of integers and we want only the even numbers.


## Imperative approach

An imperative way to do it with Javascript is to:

* create an empty array evenNumbers
* iterate over the numbers array
* push the even numbers to the evenNumbers array

## Declarative approach
But we want a more declarative way to solve this problem, and using the filter higher order function as well.

## Summary of code:
* we have a list of people (with name and age).
* we have a function olderThan21. In this case, for each person in people array, we want to access the age and see if it is older than 21.
* we filter all people based on this function.

## Map
The idea of map is to transform a collection.
The map method transforms a collection by applying a function to all of its elements and building a new collection from the returned values.

## Reduce
The idea of reduce is to receive a function and a collection, and return a value created by combining the items.
A common example people talk about is to get the total amount of an order. Imagine you were at a shopping website. You’ve added Product 1, Product 2, Product 3, and Product 4 to your shopping cart (order). Now we want to calculate the total amount of the shopping cart.

## We want the total amount of all books in our shopping cart. Simple as that. The algorithm?
filter by book type
transform the shopping cart into a collection of amount using map
combine all items by adding them up with reduce.

## Refactoring JavaScript for Performance and Readability (with Examples!)

## Scenario 1
We're an URL-shortening website, like TinyURL. We accept a long URL and return a short URL that forwards visitors to the long URL. We have two functions.

 Problem: what happens if getLong is called with a short URL that isn't in the store? Nothing is explicitly returned so undefined will be returned. Since we're not sure how we're going to handle that, let's be explicit and throw an error so that problems can be spotted during development.

Performance-wise, be careful if you're iterating through a flat array very often, especially if it's a core piece of your program. The refactor here is to change the data-structure of URLstore.

Currently, each URL object is stored in an array. We'll visualize this as a row of buckets. When we want to convert short to long, on average we need to check half of those buckets before we find the correct short URL. What if we have thousands of buckets, and we perform this hundreds of times a second?

The answer is to use some form of hash function, which Maps and Sets use under the surface. A hash function is used to map a given key to a location in the hash table. Below, this happens when we place our short URL into the store in makeShort and when we get it back out in getLong. Depending on how you're measuring run time, the result is that on average we only need to check one bucket — no matter how many total buckets there are!

## Scenario 2
We're a social media website where user URLs are generated randomly. Instead of random gibberish, we're going to use the friendly-words package that the Glitch team works on. They use this to generate the random names for your recently created projects!

It's often said that a function should do one thing. Here, createUser does one thing .. kinda. It creates a user. However, if we're thinking ahead to the future, there's a good chance (if our business is successful) that this function is going to grow very large indeed. So let's start early by breaking it up.

You may have also noticed that there is some duplicated logic in our random functions. The friendly-worlds package also offers lists for 'teams' and 'collections'. We can't go around writing functions for every option. Let's write one function that accepts a list of friendly things.


## Strategies
Here are some straightforward to implement methods that can lead to easier to read code. There are no absolutes when it comes to clean code — there's always an edge case!

* Return early from functions
* Cache variables so functions can be read like entences
* Check for Web APIs before implementing your own functionality
