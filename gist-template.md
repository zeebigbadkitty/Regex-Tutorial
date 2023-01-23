# Regex Tutorial: Matching an E-mail Address

What does "regex" mean? It's short for "regular expression" which in programming or computer science is used to define a search pattern in text form (or rather, in the form of a string.) Even that definition can cause some pause, so I'll elaborate further to say that these expressions are capable of matching a portion of a string and therefore validating that a given input matches a specified criteria or set of rules. 

## Summary

So... what does a regular expression look like? 

``` /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ ```

The expression we'll be talking about today is the regular expression that defines the search pattern for a "valid" e-mail address. We can recognize an expression because it is encased between two backward slashes (//) Remember: these expressions validate that a given input matches a specified criteria. Let's learn how! 


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)
- [Conclusion](#conclusion)

## Regex Components

There are a handful of components that make up a regular expression, or regex, and we'll go over them one by one!

### Anchors

When we talk about anchors, we're talking less about the specific text we're matching, and more about it's position. When you see a carat (^) in a regex expression, it signifies the beginning of a string (or a  line, if it's a multiline expression.) The other character you'll see that has to do with positioning is the dollar sign ($); this tells us where the string (or line) ends. We could also talk about word boundaries (or non-word boundaries) in this section which are denoted by a slash and either a lowercase or capital 'b' (/b, or /B.) When a lowercase 'b' is used, it signifies that there is in fact a word boundary (the word is ending,) while the uppercase 'B' is used when there isn't a word boundary; this could be the first character of a string, or between two characters of a string, separating a word and non-word character. 

(For the purpose of our expression, word boundaries aren't used.)

### Bracket Expressions

To me, the most recognizable portion in a regex expression are what's in between the square brackets; nested inside these brackets are the range of characters that are permitted in your expression. To explain further, let's look at our example. 

```[a-z0-9_\.-]```

If we look at our first bracket expression, it tells us that the characters a-z as well as the numbers 0-9 can be contained in our string. This also tells us that special characters such as an underscore, backslash, period, and hyphen are permitted. The important take away from this section is that the characters within these brackets define a range of possible characters in that segment of your expression. 

We'll circle back on other characters that may be included inside brackets in a later segment. 

### Quantifiers

Just like you would think based on the name, quantifiers help identify the quantity of characters to match. They can also specify the number of instances of a group in a string. The idea here is that the quantifier will tell us how many times something is repeated. 

((What do they look like?))


### Grouping Constructs

So what if we have multiple bracket expressions? These can be grouped together and can act as a single unit by wrapping them in parenthesis (kind of like the order of operations in mathematics.)

``` /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ ```

Notice again in our example that there are multiple bracket expressions encased in parenthesis; this is to group them and order them. 

### Character Classes
These are the special roles that certain characters play within a given expression and they are indicated by a backslash. Here is an incomplete listing of the following characters that have these roles: 

1. /s and /S: ((spaces))
2. /d and /D: ((digit))
3. /w and /W: ((word))

Another example of a special role that a character can play are anchors; remember /b and /B? Their special role was to show us the boundaries of a word. 

### Flags
Another grouping of characters that have a special job to do are flags; when we come across a flag, we take a specific action. Here are some examples: 

* g: searches for a pattern of groups, or an occurrence of groups. 
* i: makes the search non-case sensitive. 
* m: enables multi lines; lines begin with a carat (^) and end with a dollar sign ($.)
* u: enables the use of unicode. 

### Character Escapes
So what if we want to use one of these nifty characters in our expression just as they are. If we want to match the actual character, we add a backslash to "escape" that rule that is typically applied to that character. 

### The OR Operator

Within your expression an "or" operator may be found, or a pipe, similar to the operator we use in other programming languages. 

``` (this|that)```

### Conclusion

Given everything that's listed above, let's take a look at our example: 

``` /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ ```

((What does it all mean?))

## Author

My name is Candice and I'm a student currently enrolled in a fullstack bootcamp. I'm coming into programming with only a medical background and a desire to learn something new. You can reach me via Github at the [link posted here.](https://github.com/zeebigbadkitty)
