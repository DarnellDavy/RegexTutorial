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
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors

### Quantifiers

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
