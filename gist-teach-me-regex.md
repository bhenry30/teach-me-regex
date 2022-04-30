# Teach Me Regex

Teach Me Regex is a tutorial explaining some components of regex, illustrating different components with an example expression

## Summary

I will be walking you through this regular expression used for matching a hex value: /^#?([a-f0-9]{6}|[a-f0-9]{3})$/

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
Anchors assert something about the string or matching process. A caret `^` and dollar sign `$` are both anchors. A caret asserts position at start of the string, and a dollar sign asserts the position at the end of the string. So in our example  `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/` our string starts with zero or one `#` (because of the `?` quantifier, which I will cover next), and the sequence will end with a digit or letter.
### Quantifiers
Quantifiers tell the regex engine to match a specific quantity of what is immediately to the left (or inside) of the quantifier. Asterisks `*`, plus signs `+`, question marks `?`, and curly braces `{}` are all used as quantifiers. In the our example, the question mark asserts that the `#`, which is the preceding token in the sequence, is optional. We also see curly braces with `6` and `3` in them, meaning a matching string will either have six or three characters following the optional `?`.
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
