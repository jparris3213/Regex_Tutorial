# Regular Expressions and You: An Analysis

RegEx, or Regular Expressions, is a type of object made of a sequence of characters that are used for identifying strings and data by specific characters.

These characters are represented within a Regular expression using both specific (or literal) and general (or meta) characters.
This can be used to search and maniuplate data under any number of different scenarios.


## Summary

The Regular Expression I will be discussing tonight is for finding any Hex Value within a string.
Hex Values are commonly used for Color tags across the Internet. Though this only scratches at the surface of their usefulness.
Either way, they are commonly typed as: #FF6633. This example is used for a light red almost orange graident.
If I were looking for ANY type of Hex Value, we would use the following Regular Expression:

`/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

within this Regular Expression, while it appears gibberish means the following:

 -   Begin the search for a String that contains the starting `#` symbol
 -   Then looks for any text that has either 6 instances of any letter or number
 OR
 -  looks for a string that has 3 instances of any letter or number

 I know this may seem confusing, but that's ok, I'll break it down below.

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

We will be looking at this Regular Expression for Hex Codes, which as you can see here, being a literal, beings and ends with the character of `/`

`/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

### Anchors
The Anchors within this expression `^` and `$` indicate to that this RegEx begins with the character following the `^` (in this case a `#`)
as well as the last character before the `$` symbol, which in this case is dictated by a few quantifiers and Constructs, which we will discuss here


### Quantifiers

Quantifers help to limit the number of iterations or types of patterns the RegEx returns, as even though the line above looks difficult, a lack of quantifiers would make it even longer. In this instance we see the two quantifiers `{6}` and `{3}` used to indicate the two versions of the expression being searched.

### Grouping Constructs

I mentioned in #Quantifiers that the two quantifers " `{6}` and `{3}` " indicated two Versions of the Expression being within the Reg Ex above. What this alludes to is that between the two search string, which is all contained within a `()` section, there is a simple line `|` that in this case represents the OR operator, giving that they string wishes to look for either the expression `#([a-f0-9])` with the letters a-f or 0-9 repeated six times OR `|` repeated 3 times.

### Bracket Expressions

Now the thing about explaining some things within development is to explain one thing you have to circle back to explain something you used to explain the first place. That said, above I referenced the expression `([a-f0-9])` and that it is repeated `{6}` or `{3}` times. This is known as a Bracket expression as it searchs for any characters described within the `[]` brackets `{}` times OR `|` it will look for `[a-f0-9]` `{}` as many times as it shows up in the document or file.

### Character Classes

Character classes are used to help dictate exactly what is searched for, though within this example it is meant to be more specific so it doesn't use as many of these. If instead of A-F, Hex Codes could use the letters between F-Z, you would use a Character Class `\w` to find any character from the latin alphabit, upper or lower case, or any number, as well as the Underscore `_`

### The OR Operator

The OR Operator was described in the Bracket Expression section. But to summarize the `|` character seperates bracket expressions from each other to create multiple scenarios to cover variations to strings

### Flags

While not used in this example, Flag expressions can be used at the end of an expression (IE after the second `/`) to dictate parameters as to where to search within the string as well as which instances to ignore or accept.

- `g` This regex should return all possible matches, even ones that are not the same case (upper or lower)
- `i` This Flag ignores cases where the character case (upper or lower) does not match
- `m` This will treat each line in a multi-line string as individual strings for searching.

### Character Escapes

the Character Escape  `\` is used to indicate that the letter after it is meant to be considered a character being searched and not the a Flag, OR, Character Class, or anything starting or ending a bracket. For example, if you need to search for something using `{` you would 'escape' out of it using an expression like `\{`  within a search

## Author

Jacob Parris is a web developer currently working and learning within UNC's Web Dev BootCamp.
[Github Link](github.com/jdparri3213)