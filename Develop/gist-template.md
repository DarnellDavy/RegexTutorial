# Regex Tutorial

The following documentation will attempt to explain the components of regular expressions (regex) and how they are used for many purposes, one of which is to validate a hexadecimal color code.

## Summary

The following regex is used when validating a hexadecimal color code:

        /^#?([0-9a-f]{6}|[0-9a-f]{3})$/i

The values are validated based on the following rule sets:

* Optionally begins with a hash (`#`)

* Must be 3 *or* 6 characters in length

* Uses the letters `a-f` and/or digits from `0-1`

* Case insensitive

* All expressions must be valid to pass


The following are examples of hexadecimal color codes that will pass:

    // Examples
    #ffffff
    #FFF
    #fFfFfF
    #000
    #1f2f3F
    #345678

The following are examples of hexadecimal color codes that will fail:

    // Examples
    #fffff => // 5 characters
    #fF => // 2 characters
    #1f2f3T => // uses invalid character "T"

Here's a brief breakdown of the validation occuring with the regex expression `/^#?([0-9a-f]{6}|[0-9a-f]{3})$/i`:

* ( `/` )
    * marks the opening of the regex

* ( `^` )
    * asserts position at start of the string

* ( `#` )
    * matches the hastag character `#`

* ( `?` )
    * matches the previous token but makes that token optional

* Capuring Group `([0-9a-f]{6}|[0-9a-f]{3})`

    * Option 1 (uses 6-character hexadecimal value):
        * Match a single character from the following regex `[0-9a-f]{6}`:
            * `0-9` matches a single character in the range between 0 and 9
            * `a-f` matches a single character in the range between a and f (*case insensitive*)
            * `{6}` matches the previous token exactly 6 times
    * Option 2 (uses 3-character hexadecimal value):
        *  Match a single character from the following regex `[0-9a-f]{3}`:
            * `0-9` matches a single character in the range between 0 and 9
            * `a-f` matches a single character in the range between a and f (*case insensitive*)
            * `{3}` matches the previous token exactly 3 times

* ( `$` )
    * asserts position at the end of the string

* ( `/` )
    * marks the ending of the regex

* ( `i` )
    * match case insensitive on entire regex

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components

### Anchors

The regex example `/^#?([0-9a-f]{6}|[0-9a-f]{3})$/i` uses 2 anchors, ( `^` ) and ( `$` ). The ( `^` ) symbol indicates the beginning of a string while the ( `$` ) symbol indicates the end of a string. For reference the string is what we're looking to validate.

Anchors are unique in that they match a position within a string, not a character. Thus, in the example above both the achors indicate the beginning and the end of the string we're looking to match, not a specific character.

### Quantifiers

Quantifiers indicate that the preceding token must be matched a certain number of times. By default, quantifiers are greedy, and will match as many characters as possible.

While there are seeveral different qualifiers, the regex `/^#?([0-9a-f]{6}|[0-9a-f]{3})$/i` only uses 3 basic quantifiers, technically only 2 different quantifier types. 

The ( `?` ) is called an optional because the regex considers the token/character preceding the ( `?` ) to be optional, and will return matches with and without the specified token, basically making that token nonexistant. For the expression, the ( `?` ) character is preceded by the ( `#` ) token, meaning the regex will return matches with and without the ( `#` ) character attatched. 

Below is another good example of an optional quantifier:

        // Example
        colou?r => // accepts "color" or "colour"

The second type of quantifier used in the regex is called a quantifier and is expressed as `{6}` and `{3}`. This quantifier type matches the specified quantity of the previous token. For example, `{1,3}` will match 1 to 3, `{3}` will match exactly 3, and `{3,}` will match 3 or more.

Here's the first part of the regular expression:

        [0-9a-f]{6}

Here we're saying, "validate if the string matches any of the following characters `0-9` or `a-f` and is 6 characters in length exactly (`{6}`)".

The second part of the expression is very similiar to the first:

        [0-9a-f]{3}

This is almost the same as the first quantifier, but here we're saying "validate if the string matches any of the following characters `0-9` or `a-f` and is 3 characters in length exactly (`{3}`).

### OR Operator

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
