# Computer Science and Regular Expressions

This is a gist about regular expression terms.

## Summary

I will explain each regex below and give code examples.

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
Regex components are keyboard characters that stand for something else. They all have a meaning and usage. 

Some examples of basic regex components are:  (   )   [   ]  {   }   ^   $   .   \   ?   *   +   |
### Anchors
Regular expression anchors that allow you to match a position before or after characters. The caret anchor matches the beginning of the text. The dollar anchor matches the end of the text. let isValid = /^\d\d:\d\d$/.test('12:05'); This checks if an input string matches a time format hh:mm like 12:05.
### Quantifiers
Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found. *	*?	Matches zero or more times. 

+	+?	Matches one or more times. 
?	??	Matches zero or one time.
{ n }	{ n }?	Matches exactly n times.
{ n ,}	{ n ,}?	Matches at least n times.
{ n , m }	{ n , m }?	Matches from n to m times.
### Grouping Constructs
Grouping constructs delineate the subexpressions of a regular expression and capture the substrings of an input string. 
(expr)	Match or capture group. Captures the information that matches the expression in parentheses
(?:expr)	Non-capturing group. Groups the contained expressions together (e.g., to apply a quantifier to multiple symbols at once), but does not restrict the information to be captured to only that group.
(?=expr)	Captures information that is followed by the expression if the expression is true and the input matches the pattern that follows this expression.
(?<>)	Named capture group.*
\k<>	Named back reference. *
### Bracket Expressions
Bracket expressions can be used to match a single character or collating element.

[abcd]	Matches any character in the square brackets.
[to]	Matches any character in the range of characters separated by a hyphen (-).
[^ abcd] Matches any character except those in the square brackets or in the range of characters separated by a hyphen (-).
[.ab.]	Matches a multi-character collating element.
[= a =]	Matches all collating elements with the same primary sort order as that element, including the element itself.
### Character Classes
With a “character class”, also called “character set”, you can tell the regex engine to match only one out of several characters.

You could use this in gr[ae]y to match either gray or grey.
### The OR Operator
Returns either one OR the other. 

|	An OR character

abc | 123 this would be either abc OR 123 returns true.
### Flags
Regular expressions may have flags that affect the search.

There are only 6 of them in JavaScript:

i
With this flag the search is case-insensitive: no difference between A and a (see the example below).
g
With this flag the search looks for all matches, without it – only the first match is returned.
m
Multiline mode (covered in the chapter Multiline mode of anchors ^ $, flag "m").
s
Enables “dotall” mode, that allows a dot . to match newline character \n (covered in the chapter Character classes).
u
Enables full Unicode support. The flag enables correct processing of surrogate pairs. More about that in the chapter Unicode: flag "u" and class \p{...}.
y
“Sticky” mode: searching at the exact position in the text (covered in the chapter Sticky flag "y", searching at position)
### Character Escapes
The backslash (\) in a regular expression indicates one of the following:

The character that follows it is a special character, as shown in the table in the following section. For example, \b is an anchor that indicates that a regular expression match should begin on a word boundary, \t represents a tab, and \x020 represents a space.

A character that otherwise would be interpreted as an unescaped language construct should be interpreted literally. For example, a brace ({) begins the definition of a quantifier, but a backslash followed by a brace (\{) indicates that the regular expression engine should match the brace. Similarly, a single backslash marks the beginning of an escaped language construct, but two backslashes (\\) indicate that the regular expression engine should match the backslash.


Escaped Characters

\\

single backslash

\A

start of a string

\b

word boundary. The zero-length string between \w and \W or \W and \w.

\B

not at a word boundary

\cX

ASCII control character

\d

single digit [0-9]

\D

single character that is NOT a digit [^0-9]

\E

stop processing escaped characters

\l

match a single lowercase letter [a-z]

\L

single character that is not lowercase [^a-z]

\Q

ignore escaped characters until \E is found

\r

carriage return

\s

single whitespace character

\S

single character that is NOT white space

\u

single uppercase character [A-Z]

\U

single character that is not uppercase [^A-Z]

\w

word character [a-zA-Z0-9_]

\W

single character that is NOT a word character [^a-zA-Z0-9_]

\x00-\xFF

hexadecimal character

\x{0000}-\x{FFFF}

Unicode code point

\Z

end of a string before the line break
## Author

Github: https://github.com/holgateb
