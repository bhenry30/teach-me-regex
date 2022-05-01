# Teach Me Regex

Teach Me Regex is a tutorial explaining some components of regex, illustrating different components with an example expression

## Summary

I will be walking you through this regular expression used for matching a hex value: `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

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
The OR Operator `|` lets us match a string that contains the character on either side of the `|` in that specific place in the sequence. In our example, `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`, we are asserting that matching results can either have `[a-f0-9]{6}` (6 characters of digits/letters) or (`|`) `[a-f0-9]{3}` (3 characters of digits/letters).

### Character Classes
A character class defines a set of characters. Many character classes are represented by a character following a backslash. For example, `\d` matches any digit, just like `[0-9]`. `\w` matches any alphanumeric character (including the undescore). The bracket expression of this would be `[A-Za-z0-9_]`. Another useful character class expression is `\s`, which matches any whitespace.

### Flags
Flags appear at the end of an expression (after the ending forward slash `/`) and define additional limits or functionality. `g`, `m`, and `i` are common flags. For example, `i` makes the expression case-insensitive; so `/The/i` would match `the`.

### Grouping and Capturing
Parentheses `()` create a capturing group. Grouping and capturing is very useful for extracting information from strings or data using a programming language for possible re-use. Each section that in parentheses is known as a subexpression. In our hex code-matching example, `[a-f0-9]{6}|[a-f0-9]{3}` has parentheses around it, declaring it as the `group 1` subexpression.

### Bracket Expressions
Bracket Expressions are anything inside a set of square brackets `[]`. Bracket expressions represent a range of characters we want to match. `[the]` will look for a string that includes `t` or `h` or `e`. We often use a hyphen `-` between characters in bracket expressions to represent a range of characters; so `[a-h]` will match any string that has any letter `a` through `h` in it. In our hex code example, `[a-f0-9]{6}` matches any 6 characters (represented by `{6}`) between `a` and `f` and `0` and `9`. 

### Greedy and Lazy Match
By default quantifiers are "greedy", which means they will match as many characters as possible. Making a quantifier "lazy" causes it to match as few characters as possible. A question mark `?` after a quantifier makes it lazy. 

### Boundaries
Boundaries are assertions about the engine's current position in the string. `\b` is a word boundary that matches positions where one side is a word character and the other side isn't. For example, `\bThe\` would match `The` but not `These`.

### Back-references
Back-references match the same text as the related capturing group (remember those ) in the expression and are represented by using a backslash followed by the group number you want to match. So `\1` would match `group 1`. In our hex code example, `\1` would match `[a-f0-9]{6}|[a-f0-9]{3}`.

### Look-ahead and Look-behind
Look-ahead and look-behind (or together, lookaround) allow us to find matches based on what is followed by or preceding our pattern. For example, if we wanted to match the characters preceding the `@` in someone's email address that they fill in a form, we could use the lookahead `(?=@)` preceded by `.+`, which would match any character that occurs between one and unlimited times before `@`. The full expression would be `.+(?=@)`.

## Author
Brandon Henry is a full stack web developer from Austin, TX. You can contact him and find more of his projects at https://github.com/bhenry30
