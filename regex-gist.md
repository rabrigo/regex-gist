# Regex Gist

A gist explaining the hex value regex provided in the develop folder of homework assignment 17.

## Summary

This regex, `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`, provides the following criteria to be met: a string that may or may not start with a # symbol, includes lowercase letters from a to f or numbers, either three or six characters long.

This expression is a literal, so it is enclosed in forward slashes /. The ^ symbol denotes an anchor tag, signifying that this string will start with the proceeding character #. The question mark after the number sign however, is a lazy quantifier. In the way it is written, the preceding character (the #) may be included zero times or once. Both parenthesis notate the start and end of a group. This group includes criteria for a string with lowercase letters within a through f or numbers, three or six digits long (character lengths specified in the proceeding curly brackets). The single vertical line symbolizes the OR operator, that either the first or second subexpression may be true to fulfill the requirements.

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

### Anchors

This expression is a literal, so it is enclosed in forward slashes /. The ^ symbol denotes an anchor tag, signifying that this string will start with the proceeding character #.  The $ sign also denotes an anchor tag. Specifically, it symbolizes that the string will end with the preceding characters (the criteria specified within the group constructor).

### Quantifiers

The question mark after the number sign however, is a lazy quantifier. In the way it is written, the preceding character (the #) may be included zero times or once. #aaa000 or aaa000 would meet the requirements specified by this regex.

### Grouping Constructs

The open and close parenthesis notate the start and end of a group. In this case, it encloses two subexpressions [a-f0-9]{6}|[a-f0-9]{3}.

### Bracket Expressions

Within the two sets of brackets are two subexpressions--a string with lowercase letters within a through f or numbers a-f0-9. The proceeding curly brackets symbolize the character length specified by the number within. In this case, [a-f0-9]{6} specifies the string must pass the previously mentioned criteria with 6 characters and [a-f0-9]{3} with 3 characters.

### Character Classes

The character classes for this regex are as for lower cased letters within a to f and numbers. This was defined within the brackets. The hyphen between the two characters a-f denote the range between the two. It also case sensitive. The string #aae001 would pass this regex but not #AAE001.

### The OR Operator

The single vertical line right after indicates that either the previous subexpression or the following one may be met to fulfill the regex's criteria. For instance, aab300 and aab would both meet the criteria of this expression.

### Flags

In this case, there are no flags. These would be included after the last forward slash. For instance, if the following were included after the second slash: g (global search), i (case insensitive), and m (multi-line search).

### Character Escapes

We don't have any for this regex. However, this would allow for a character to be included in the criteria of the expression but might normally be interpreted as part of structure or syntax. For instance, if you wanted to require a string that starts with an opening bracket, and has three lowercase letters within a through f, you could write `/^\[[a-f]{3}$/`. These would pass this regex: `[abc` `[aaa` `[bbb`

Above, we included a backslash in front of the opening bracket to specify that this opening bracket will actually be the starting character of said string. If we didn't have the backslash, then it could be interpreted as the beginning of a bracket expression without a closing bracket.

## Author & Acknowledgements

My name is Ronnel and here is my GitHub profile: https://github.com/rabrigo

A big thank you to the following websites for helping me understand regex.

https://coding-boot-camp.github.io/full-stack/computer-science/regex-tutorial
https://regex101.com/
