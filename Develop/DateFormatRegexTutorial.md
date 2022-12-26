# Date Format Regex Tutorial

This tutorial will walk you through the components of a regex (regular expression) used to match dates with dashe, slashe or space separators (e.g. dd-mm-yyyy dd/mm/yyyy dd mm yyyy).

## Summary

In this tutorial, you'll see the regex used to match to the dd/mm/yyyy date format. The regex is as follows:

`/^(0?[1-9]|[12][0-9]|3[01])([ \/\-])(0?[1-9]|1[012])\2([0-9][0-9][0-9][0-9])$/`

The express that defines the date is held between the two slashes `/ /`. 

The expression begins with matching the day which can be 1 to 31. It starts with a check of the first index (the index starts with 0). The first index can be numbers between 0 and 9. If the first index number is 1 or 2, then numbers 0 to 9 can be used next. If the first index number is 3, then only 0 or 1 may be used next. 

After matching the day a separator of ` `, `/`, or `-` may be used. 

Next, the expression matches the month, which can be 1 to 12. Similar to matching the day, it starts by checking the first index, which can be 0 to 9. If the first index is 1, then the next number can only be 0, 1, or 2. 

After matching the month a separator of ` `, `/`, or `-` may be used again. the `\2` is used to repeat the second section in the expression `([ \/\-])`.

Finally, the year can be matched to any number between 0 and 9999.

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

Two achors are used this regex, `^` and `$`. `^` is used at the start to determine the starting string, the day in this case `(0?[1-9]|[12][0-9]|3[01])`, and `$` is used at the end to determine the ending string, the year `([0-9][0-9][0-9][0-9])`.

### Quantifiers

The quantifer `?` is used twice in this regex, once for the day and once for the month. `?` is a shorthand of `{0-1}`, which quantifies how many times an expression or symbol can be used. `{0-1}` is used to make the previous symbol optional since it can be used zero or 1 times. In the date format regex, `0?` can be use to include a leading zero, but it will also match to an expression without leading zeros. As an example, it can match to `01/01/2000` or `1/1/2000`.

### Grouping Constructs

`()` are used to group the regex into sub expressions. This regex is dived up into 4 groups, the day: `(0?[1-9]|[12][0-9]|3[01])`, a separator: `([ \/\-])`, the month: `(0?[1-9]|1[012])`, and the year: `([0-9][0-9][0-9][0-9])`. These groups are captured and numbered 1 through 4 and backrefences can be used to repeat the group. In this regex, the backreference `\2`is used to repeat the separator group between the month and year instead of repeating the group again.

### Bracket Expressions

### Character Classes

### The OR Operator

### Flags

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
