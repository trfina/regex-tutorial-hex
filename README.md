# <b>Regex Tutorial:  Matching a Hex Value</b>

Regular expressions (Regex) are used by Data Scientists and other IT professionals to extract and process data into data sets that meet certain criteria.

Web scraping, search and replace, and pattern matching are but a few of the many tasks that can be accomplished with regular expressions.

## <b>Summary</b>

This tutorial describes how to match a <b>hex color code value</b> using Regex:

> `/^#?([a-f0-9]{6}|[a-f0-9|{3})$/`

Hexidecimal Color Values (Hex Codes) are primarily used in style sheets to represent color values for a computer screen.  A hex color code begins with `#`, followed by three sets of two-digit hex numbers, i.e. (#01ff04). Each set of hexidecimal numbers represents the colors red, green and blue, respectively.  A hex color can also be represented by 3 characters (shorthand or hex-triplet), if each set of the two-digit hex numbers use the same characters.

For Example:
* #000000 represents no red, no green and no blue, which equates to black in the color spectrum.
* #FFFFFF represents max red, max green and max blue, which equates to white in the color spectrum.
* #000 is the shorthand/hex-triplet representation of black.
* #FFF is the shorthand/hex-triplet representation of white.
* #0d98ba is a medium shade of dark cyan


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

# Regex Components

## Matching the Hex Color Code Value 
`/^#?([a-fA-Z0-9]{6}|[a-fA-Z0-9]{3})$/`

## Anchors 
### MChars ^ and $

#### Anchors define where the search parameters begin and end while parsing through a string of data.

In the hex color value regex **`^`**`#?([a-fA-Z0-9]{6}|[a-fA-Z0-9]{3})`**`$`**:

- `^` indicates the beginning of the search string
- `$` indicates the end of the search string

Additional examples:
- `^abc` will search for string or line that begins with `abc`
- `abc$` will search for a string or line that ends with `abc`


## Quantifiers
### MChars  *, +, ?, and {}

#### Quantifiers match a number of instances of a character, group, or character class in a string.

- `*` - match 0 or more of previous expression
- `+` - match 1 or more of previous expression
- `?` - match 0 or 1 of previous expression
- `{n}` - explicit number or a range of matches

The hex color regex `/^#?([a-fA-Z0-9]{6}|[a-fA-Z0-9]{3})$/` uses  `?`, `{6}` and `{3}` to quantify the string.

- `#?` matches a hex color code for 0 or 1 of an instance of the `#` character.  This means that all hex codes are considered a match whether it has the `#` preceding the color code or not.

>All color codes used in style sheets have the `#` preceding the color code, right?  Why would it be excluded?
>One example is that in order to save storage space the `#` symbol is excluded from a hex color code in databases when one color schema is converted to another.

- `{6}` quantifies that up to six characters in the explicit set [a-zA-Z0-9] can be matched.  `{3}` quantifies up to three characters of [a-zA-Z0-9] to be matched.

Additional examples:
- `xyz*` matches a string that has `xy` followed by 0 or more `z` characters
- `xyz+` matches a string that has `xy` followed by 1 or more `z` characters
- `xyz{3}` expects the string  `xy` followed by 3 `z` characters
- `xyz{2,10}` matches a string that has `xy` followed by 2 up to 10 `z` characters


## OR Operator
### MChars | or []

#### The OR Operator matches a string before or after the | (alternation).  
#### [...] contains a range of characters for the match.

- The hex color code regex has `[a-fA-Z0-9]{6}` **|** `[a-fA-Z0-9]{3}`, meaning either `[a-fA-Z0-9]{6}` OR `[a-zA-Z0-9]{3}` returns a true value.

Additional examples:
- `soup|salad` returns true for either `soup` or `salad`
- `a[bc]d` returns true for either `abd` or `acd`


## Character Classes
### \d, \w, \s, [0-9a-fA-F], `[abc]` 

#### Character classes allow you to match a set of characters including digits, whitespace and a range of characters.

- `[0-9a-fA-F]` is used in the hex color code regex and will match a range of characters by using a hyphen.  This example will match digits 0-9, and a-f, lower and upper case.
- `\d` matches any decimal digit, whereas `\D` matches any nondigit
- `\w` matches any word character, `\W` for any nonword character
- `\s` matches any white-space character, `\S` any non-white-space character

Additional examples:
- `[a-z&&[^aeiou]]` matches a single letter that is not a vowel
- `[abc]` matches `a`, `b` or `c`


## Bracket Expressions
### MChar []

#### Individual characters between the brackets will be matched as well as a set of characters

- The snipet `[a-fA-Z0-9]` from the hex color code will match characters from the sets `a-f`, `A-F` or `0-9`.  Other quantifiers can be applied to the brackets in the regex as well.

Additional examples:
- a[bB]c matches abc or aBc
- [^567] matches all characters except `5`, `6`, or `7`


## Greedy and Lazy Match

 Greedy operators expand a match with all characters in the search critera.  Therefore, it finds the longest match. 

 - `#09AF6B` (Jade) -  In the hex color code example, the longest match would be the expanded 6 character hex color code with the `#` symbol.

 Lazy matches optional characters.  Therefore, it finds the smallest possible string.

 - `3C9` (Crayola Shamrock) - The smallest possible string would be a hex-triplet, or a shorthand version of the expanded 6 character hex code without the `#`.


## Resources

* [Understand Hex Color Codes](https://www.codeconquest.com/hex-color-codes/)

* [Applications of Regular Expressions](https://www.analyticsvidhya.com/blog/2020/01/4-applications-of-regular-expressions-that-every-data-scientist-should-know-with-python-code/)

* [Regex Character Classes](https://www.regular-expressions.info/refcharclass.html)

* [Regex Simplified](https://ionlake.zendesk.com/hc/en-us/articles/360031442771-Regex-Simplified-by-Jonny-Fox)


### Author
  
- [GitHub Profile](https://github.com/trfina)
- Additional Questions?  Contact me at finatammy@gmail.com

This README was generated with ❤️ by Tammy Fina © 2022
