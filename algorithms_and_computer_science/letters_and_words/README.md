# Letters and Words
Words are a pretty big part of society. It's only fair computers have some means
to interact with them! In JavaScript, the [data
type](http://glossary.codeunion.io/data-types) that represents letters and words
is known as a [string](http://glossary.codeunion.io/string-data-type)


Before you get started, I'd recommend skimming the [documentation for 
strings](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#Description).
Of particular interest are:
 * [The description](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#Description).
 * [The list of
   properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#Properties_2).
 * [The list of
   methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#Methods_2).

## Instructions

1. Run `node` in your terminal.
2. Solve each of these exercises:
  * Replace the `__` with your solution in the `node` terminal.
  * Verify the code does what you think it should
  * Replace the puzzle in this readme with your solution.
  * Include a link to the documentation for the method you used to solve the
    problem.
  * Verify your solution works by copy-pasting it back into node.
5. Commit!


## Exercises
### How Long Is That?!

Can you get the computer to tell you how long a string is?

```javascript
"hi there".__
// Should evaluate to 8
"what's happening?".__
// Should evaluate to 17
```

### Replace, plz.
How about swap some words around?

```javascript
"Pretty sure zee is the lamest".__("lamest", "coolest")
// Should evaluate to "Pretty sure zee is the coolest"

"Dead men tell no tales".__("tales", "rails")
// Should evaluate to "Dead men tell no rails"
```

### What's inside?
Maybe find a string inside a string?

```javascript
"What kind of madness is this?".__("madness")
// Should evaluate to [ 'madness', index: 13, input: 'What kind of madness is this?' ]
"When there is nothing you can find".__("something")
// Should evaluate to null
```

### Break it apart!
Can you turn a string into an array?

```javascript
"Hey there voters!".__(" ")
// Should evaluate to [ 'Hey', 'there', 'voters!' ]
"Such a character!".__("")
[ 'S', 'u', 'c', 'h', ' ', 'a', ' ', 'c', 'h', 'a', 'r', 'a', 'c', 't', 'e', 'r', '!' ]
"eggs, bacon, cheese, tomato, kale,".__(__)
[ 'eggs', 'bacon', 'cheese', 'tomato', 'kale,' ]
```

### Take a chunk!
How about grabbing part of the string?

```javascript
"Name: Zee".__(6)
// Should evaluate to 'Zee'
"Favorite Color: Chartreuse".__(__)
// Should evaluate to 'Chartreuse'
"Favorite Animal: Catapult".__(__,3)
// Should evaluate to 'Cat'
"Weirdest Trait: Can lick elbow".__(-14)
```

### Where Did I Put That...
How can we find the first location of a character?

```javascript
"Pork: The Other White Meat".__(':')
// Should evaluate to 4

"Moods: Happy, Sad, Grumpy".__(',')
// Should evaluate to 12

"Friend or foe?".__('E')
// Should evaluate to -1
```

### The Other Way Round!

What about the last location?

```javascript
"Groceries: avacados, bananas, strawberries, oregano".__(",")
// Should evaluate to 42
```

### Holding Hands

Could you connect some strings together?

```
"Hello".__("World")
// Should evaluate to "HelloWorld"

"Hey".__("Thats", "A", "Lot","Of","Words")
// Should evaluate to "HeyThatsALotOfWords"
```

### Escape! ESCAPE!

What happens if we want some quotes in our quotes?!

```
"They said: __"Yo__""
// Evalutes to 'They said: "Yo"'

__Or you could use a different "kind" of quotes__
// Evalautes to 'Or you could use a different "kind" of quotes'
```

### Put It Together!

Write a function that given a string of the format "Question: Answer" returns
the answer.

```javascript
function getAnswer(entry) {
}

getAnswer("Name: Zee");
// Should evaluate to "Zee"
getAnswer("Favorite Color: Orange")
// Should evaluate to "Orange"
getAnswer("Favorite Programming Language: Clojure")
// Should evaluate to "Clojure"
```