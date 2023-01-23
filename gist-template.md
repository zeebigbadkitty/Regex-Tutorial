# Regex Tutorial: Matching an E-mail Address

What does "regex" mean? It's short for "regular expression" which in programming or computer science is used to define a search pattern in text form (or rather, in the form of a string.) Even that definition can cause some pause, so I'll elaborate further to say that these expressions are capable of matching a portion of a string and therefore validating that a given input matches a specified criteria or set of rules. 

## Summary

So... what does a regular expression look like? 

``` /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ ```

The expression we'll be talking about today is the regular expression that defines the search pattern for a "valid" e-mail address. Remember: these expressions validate that a given input matches a specified criteria. Let's learn how! 


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

There are a handful of components that make up a regular expression, or regex, and we'll go over them one by one!

### Anchors

When we talk about anchors, we're talking less about the specific text we're matching, and more about it's position. When you see a carat (^) in a regex expression, it signifies the beginning of a string (or a  line, if it's a multiline expression.) The other character you'll see that has to do with positioning is the dollar sign ($); this tells us where the string (or line) ends. We could also talk about word boundaries (or non-word boundaries) in this section which are denoted by a slash and either a lowercase or capital 'b' (/b, or /B.) When a lowercase 'b' is used, it signifies that there is in fact a word boundary (the word is ending,) while the uppercase 'B' is used when there isn't a word boundary; this could be the first character of a string, or between two characters of a string, separating a word and non-word character. 

(For the purpose of our expression, word boundaries aren't used.)

### Quantifiers

### Grouping Constructs

### Bracket Expressions

### Character Classes

### The OR Operator

### Flags

### Character Escapes

## Author

My name is Candice and I'm a student currently enrolled in a fullstack bootcamp. I'm coming into programming with only a medical background and a desire to learn something new. You can reach me via Github at the [link posted here.](https://github.com/zeebigbadkitty)
