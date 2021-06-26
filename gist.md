# 17 Computer Science for JavaScript: Regex Tutorial

Regular expressions aka Regex are patterns used to match character combinations in strings. Regex patterns are composed of simple characters or a combination of simple and special characters. A regex allows you to extract information from a string by searching through all the text to find what you need. It can be anything. From numbers and letters, to punctuation, or white space. The beautiful thing about Regex, is that it  allows you to check and match any character combination found in string data. Regex is kind of like having a personalized search bar, right at your fingertips. Allowing you to create your own pattern search criteria.

## Summary

In this tutorial, I will be explaining and breaking down the matching of an email address by deciphering the code:
 
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```


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
The anchors in regex are 2 special characters that signify the beginning and end being the caret ^ and the dollar $.
You use the ^ anchor to match the beginning of the text.
And you use the $ anchor to match the end of the text.
In the case of matching an email:
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```
The ^ signifies the beginning of the email address and the $  tells the code where to end its search.

### Quantifiers

Quantifiers match a number of instances of a character, group, or character class in a string.
(*)	zero or more times
+ 	one or more times
? 	zero or one time
{}	Curly brackets can provide different ways to set limits for a match
“n” is a number
 { n }   matches exactly “n” number of times
 { n, } matches at least “n” number of times
 { n, x } matches a minimum of “n” number of times and the “x” is the maximum
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```
You can see that there are 2 + in the code.
```
/^([a-z0-9_\.-]+)   @([\da-z\.-]+)  \.([a-z\.]{2,6})$/
```
 The first one is the first part of the email address. The second one appears after the @ sign and before the period.  Meaning there is more than one input that is part of the string to be searched.  
 
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]   {2,6}  )$/
```
There is also {} with {2,6} meaning there is a minimum of 2 characters and a maximum of 6 at the end of the email address.

### Grouping Constructs

Grouping constructs depict the subexpressions of a regular expression and capture the substrings of an input string.You may check multiple parts of a string to determine if different sections fulfill the different requirements. By using grouping constructs to break the sections up.  Subexpressions are a section of code that is grouped by (())
```
/^([a-z0-9_\.-]+)   @([\da-z\.-]+)  \.([a-z\.]{2,6})$/
```
In the case of the email address we have 3  subexpressions.
 
 
``` 
/^    ([a-z0-9_\.-]+)   @     ([\da-z\.-]+)    \.    ([a-z\.]{2,6})   $/
```

### Bracket Expressions

A bracket expression is a list of characters enclosed by [  ]. Matching any single character in that list we want to include in the search.
 
 
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+) \.([a-z\.]{2,6})$/
```
 
[a-z0-9_\.-] 
 any letters a-z or numbers 0-9, including underscores, periods and hyphens.
 
[\da-z\.-]
Any letters a-z, includes periods and hyphens
 
[a-z\.] 
Letters a-z followed by a period.


### Character Classes

A character class allows you to match any symbol from a certain character set. A character class is also called a character set.
\d    is for digits 0-9
\s  for space: includes spaces, tabs 
\w  for word  A-Z, a-z,0-9, _
. = any character

### The OR Operator
The OR operator ( | ) or alternation  matches either the expression before or the expression after the operator. 
 
[abc123] is the same is (a|b|c|1|2|3)


### Flags
Flags are settings that change the searching behavior.
 
The ignore or i flag ignores cases when searching. By default, searches are case-sensitive. To search for a string with any cases, you use the i flag.
 
The global flag or g flag  looks for all matches and returns all of them. Without the global flag, the RegEx object only checks if there is a match in a string and returns the first match.

### Character Escapes
The backslash (\) in a regular expression indicates that the character that follows it is a special character or a character that otherwise would be interpreted as an unescaped language construct  that should be interpreted literally. 

Example: the open curly brace ({) is used to begin a quantifier. Adding a backslash before the open curly brace (\{) means that the regex has to look for the open curly brace character. Instead of defining the quantifier.

## Author

My name is Ariel Marchand. I'm a student currently enrolled in the Univeristy of Denver's web development bootcamp. This is my first Regex tutorial. Please feel free to follow me on [Github:](https://github.com/killjoyangel)