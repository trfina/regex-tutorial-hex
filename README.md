# <b>Regex Tutorial:  Matching a Hex Value</b>

<p>Regular expressions (Regex) are used by Data Scientists and other IT professionals to extract and process data into data sets that meet certain criteria.</p>
<p>Web scraping, search and replace, and pattern matching are but a few of the many tasks that can be accomplished with Regex.</p>

## <b>Summary</b>

<p>This tutorial describes how to match a <b>hex color code value</b> using Regex:</p>

<p style="text-align: center;">/^#?([a-f0-9]{6}|[a-f0-9|{3})$/</p>

<p>Hexidecimal Color Values (Hex Codes) are primarily used in style sheets to represent color values for a computer screen.  A hex color code begins with `#`, followed by three sets of two-digit numbers, i.e. (#01ff04). Each set of hexidecimal numbers represents the colors red, green and blue, respectivly.  A hex color can also be represented by 3 characters (shorthand or hex-triplet), if each set of the two-digits numbers use the same character.</p>

> For Example:>
> - #000000 represents no red, no green and no blue, which equates to black in the color spectrum.
> - #FFFFFF represents max red, max green and max blue, which equates to white in the color spectrum.
> - #000 is the shorthand/hex-triplet representation of black.
> - #FFF is the shorthand/hex-triplet representation of white.
> - #0d98ba is a medium shade of dark cyan

(insert references for Understanding Hex Color codes)

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

# Regex Components

## Matching a Hex Value – `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

## Anchors 
### Metacharacters ^ and $

>#### Anchors define where the search parameters begin and end while parsing through a string of data.
> In the hex color value regex **^**#?([a-f0-9]{6}|[a-f0-9]{3})**$**:
>
> - `^` indicates the beginning of the search string
> - `$` indicates the end of the search string
>
> Additional examples:
> - `^abc` will search for string or line that begins with `abc`
> - `abc$` will search for a string or line that ends with `abc`

## Quantifiers
### Metacharacters  *, +, ?, and {}

>#### Quantifiers match a number of instances of a character, group, or character class in a string.
>
> - `*` - match 0 or more of previous expression
> - `+` - match 1 or more of previous expression
> - `?` - match 0 or 1 of previous expression
> - `{n}` - explicit number or a range of matches
>
> `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`
> The hex color regex above uses  `?`, `{6}` and `{3}` to quantify the string.</p>
>
> - `?` matches the `#` character preceding a hex color code for 0 or 1 of previous string expressions.  This means that all hex codes are considered a match whether it has a `#` preceding the color code or not.
>> All color codes used in style sheets have the `#` preceeding the color code, right?  Why would it be excluded?  One explanation is that the `#` symbol is excluded from a hex color code in databases when large data sets are converted from one color schema to another in order to save storage space.
> - `{6}` quantifies that up to six characters in the explicit set [a-z0-9] can be matched.  `{3}` quantifies up to three characters of [a-z0-9] to be matched.
>
> Additional examples:
> - `xyz*` matches a string that has `xy` followed by 0 or more `z` characters</li>
> - `xyz+` matches a string that has `xy` followed by 1 or more `z` characters</li>
> - `xyz{3}` expects the string  `xy` followed by 3 `z` characters</li>
> - `xyz{2,10}` matches a string that has `xy` followed by 2 up to 10 `z` characters</li>

(add referencesregexlib.com  - Regular Expression Cheat Sheet)

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

### Author

This tutorial was created by Tammy Fina referencing the follow resources:

citation for uses of regex:
https://www.analyticsvidhya.com/blog/2020/01/4-applications-of-regular-expressions-that-every-data-scientist-should-know-with-python-code/
