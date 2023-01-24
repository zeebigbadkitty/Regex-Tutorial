# Regex Tutorial: Matching an E-mail Address

What does "regex" mean? It's short for "regular expression" which in programming or computer science is used to define a search pattern in text form (or rather, in the form of a string.) Even that definition can cause some pause, so I'll elaborate further to say that these expressions are capable of matching a portion of a string and therefore validating that a given input matches a specified criteria or set of rules. 

## Summary

So... what does a regular expression look like? 

``` /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ ```

The expression we'll be talking about today is the regular expression that defines the search pattern for a "valid" e-mail address. We can recognize an expression because it is encased between two backward slashes (//) Remember: these expressions validate that a given input matches a specified criteria. Let's learn how! 


## Table of Contents

- [Anchors](#anchors)
- [Bracket Expressions](#bracket-expressions)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [The OR Operator](#the-or-operator)
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

You can spot a quantifier by curly braces ({}) with a range nested inside. Think about the range as the minimum and maximum number of times a character or string is repeated. When there is no specified limit or range, the limit becomes infinite. 

```{1, 27}```

The above quantifier is telling us that an item should be repeated at least 1 time, and up to 27 times!

Other symbols that are quantifiers are the question mark (?), the asterisk (*), and the plus (+) sign. When you see these, try to also think of them as a range as outlined below. 

* ? ---> {0, 1}
* \* ---> {0,}
* \+ ---> {1,}

### Grouping Constructs

So what if we have multiple bracket expressions? These can be grouped together and can act as a single unit by wrapping them in parenthesis (kind of like the order of operations in mathematics.)

``` /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ ```

Notice again in our example that there are multiple bracket expressions encased in parenthesis; this is to group them and order them. 

### Character Classes
These are the special roles that certain characters play within a given expression and they are indicated by a backslash. Here is an partial listing of some of the characters that have these roles: 

1. /s and /S: denotes whitespace/spaces. This includes a traditional space, tab, or enter (when generating a new line.) The capital will search for the inverse condition.
2. /d and /D: denotes digits [0-9] and the capital will search for the inverse condition.
3. /w and /W: denotes "words." The capital will search for the inverse condition. 

Another example of a special role that a character can play are anchors; remember /b and /B? Their special role was to show us the boundaries of a word. 

If a carat (^) is used inside square brackets ([]), it has the same effect as using an exclamation point in our code; it searches for the inverse. 

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

The above line translates to "this" OR "that."

### Conclusion

Given everything that's listed above, let's take a look at our example: 

``` /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ ```

Now let's break it up into three parts.

```/^([a-z0-9_\.-]+)@```

The initial slash is telling us this is a regex expression. The carat is an anchor telling us that we're at the beginning of our string. We then have a grouping (in parenthesis) of a bracket expression. This bracket expression is validating that our search matches alpha characters a through z, as well ad numerical digits 0 through 9 (and we're to also include a underscore, period, backslash, and hyphen.) We're then going to "add" an "@" symbol with a (+) sign, meaning there has to be at least one. 

```([\da-z\.-]+)```

Following our '@' symbol, we have another grouping of square brackets. This time we have a character class of /d, which we know is a digit, and again, matches will be made with alpha characters a through z and the same special characters as our previous segment. 

```\.([a-z\.]{2,6})$/```

We want to be sure that there is in fact a period (.) after the last grouping, so we must escape that character by adding a backslash. We then have a grouping of square brackets with alpha numerical characters like we've seen before, but this time we have a qualifier that specifies that we must have at least 2 to 6 characters included in our domain portion of our e-mail address. 

All that being said, this isn't the *only* regex expression for validating an e-mail address; the can become quite complex! This one leaves quite a bit of room for returning undeliverable e-mails; there are some that use the OR (|) operator and include all available domains. As you can imagine, something that specific can change rapidly and would have to be expanded upon as more domains are created. 

## Author

My name is Candice and I'm a student currently enrolled in a fullstack bootcamp. I'm coming into programming with only a medical background and a desire to learn something new. You can reach me via Github at the [link posted here.](https://github.com/zeebigbadkitty)
