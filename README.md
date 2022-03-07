# Regex Tutorial:  Matching a Hex Value

Regular expressions (Regex) are used by Data Scientists and other IT professionals to extract and process data into a data set that meets certain criteria.

Web scraping, search and replace, and pattern matching are but a few of the many tasks that can be accomplished with Regex.

## Summary

This tutorial describes how to match a hex value using Regex, as follows:

<p style="text-align: center;">/^#?([a-f0-9]{6}|[a-f0-9|{3})$/</p>






## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

Matching a Hex Value – /^#?([a-f0-9]{6}|[a-f0-9]{3})$/

### Anchors 
^ and $

Anchors define where the search parameters begin and end while parsing through a string of data.

In the hex value example:

`^` indicates to search for the `#` character.  If found, a search for the string `([a-f0-9]{6}|[a-f0-9]{3})` is initiated as defined by the `$` anchor.

Another example:


### Quantifiers
* + ? and {}

Quantifiers match a number of instances of a character, group, or character class in a string.

### OR Operator
| or []

### Character Classes
\d \w \s and .

### Flags

### Grouping and Capturing

### Bracket Expressions
[]

### Greedy and Lazy Match
 Greedy operators expand a match with all charaters in the search critera.

 Lazy matches optional characters.

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

This tutorial was created by Tammy Fina referencing the follow resources:

citation for uses of regex:
https://www.analyticsvidhya.com/blog/2020/01/4-applications-of-regular-expressions-that-every-data-scientist-should-know-with-python-code/

