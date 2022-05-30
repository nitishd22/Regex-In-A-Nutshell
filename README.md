# Regular Expressions in a Nutshell

This gist will go over the basics of what regular expressions, or regex, are. Regex is used when matching groups of characters in a string. Common uses for regex is validation, such as validating if an entry is a valid email address, and extracting information.

## Summary

This gist will show a demonstration of how Regular Expressions can be used to match emails. This will enable developers to be able to make sure an entry is a valid email address.
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
The anchors are the beginning and end of a regex.
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
In this example, the anchors are "^" and "$". The first part has to match the
`^([a-z0-9_\.-]+)` and the end has to match with
`.([a-z\.]{2,6})$`.

### Quantifiers
Quantifiers simply show how many times one or more characters has to be there for a match. For example, in our first part,
`^([a-z0-9_\.-]+)`,
it ends with '+'. The '+' indicates that at least one of the conditions of 'a-z', "0-9", '_ ', '.', '-' must be in the string to be a match.

### OR Operator
There is no OR operator in the example email matching code. The OR operator is '|', and it will match the expression before or after depending on which one matches. It will check in order.

### Character Classes
Character classes will match only one character. In our example,
`@([\da-z\.-]+)\`,
'\d' is the character class indicator. It means that the character after '@' has to be a letter from a-z.

### Flags
This example email matching regex does not contain any flags. Flags are used after the end slash of a regex to add certain rules to the matching.

g is for "global" and means all instance within a string that follow the guidelines will be allowed

m is for "multiline" which searches by line rather than by string

i is for "insensitive" which means the expression matching will not be case-sensitive

u is for "unicode"

s will match characters even if they normally wouldn't.

### Grouping and Capturing
Grouping and capturing essentially means to separate regex into different parts to make it easier to have specific matching guidelines for each part. For example,
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`,
in this expression, each group is separated by parentheses and must be matched before moving on to the next.

### Bracket Expressions
Bracket Expressions are similar to the parentheses in grouping, but here we want to separate by brackets. The first bracket before the '@',
`[a-z0-9_\.-]`,
indicates that the string before the '@' can have a-z, 0-9, underscores, periods, and hyphens.

### Greedy and Lazy Match
There are no greedy or lazy match quantifiers in here, but essentially, a greedy quantifier will match as many instances of the character or part of string to be matched as possible. The lazy quantifier is the opposite, matching the minimum amount possible. In order to use a lazy quantifier you have to add '?' at the end.

### Boundaries
Boundaries are used to separate words or word characters, with '\b' and '\w' respectively. It also functions as an anchor due to its nature. There are no boundaries in the email matching code.

### Back-references
Back-references refer to the previously matched text before the current group. There are no backreferences in our example. Typing in '\1' after a statement with multiple groups will reference the first group. '\2' will do the second, and so forth.

### Look-ahead and Look-behind
Look-aheads and look-behinds are used to check if groups after and before match.
- '(?=text)' is a positive look-ahead and it will match a group after and won't include it in the result.
- '(?!text)' is negative and will show if a group after won't match. If it does, the result is deleted.
- '(?<=text)' is a positive look-behind and it will match a group before and won't include it in the result.
- '(?<!text)' is a negative look-behind and will show if a group before does not match the expression. If it does, the result is deleted.

## Author

By Nitish Doss
- GitHub: https://github.com/nitishd22
