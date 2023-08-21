# Email Regex Tutorial

## Summary

For web developers, ensuring the accuracy of user inputs within different types of forms is crucial. As this marks the inception of data between the client and the server, it is essential to establish a solid foundation. Forgoing this step could result to complications on the server-side validation, which makes it difficult to complete the necessary tasks. To solve this issue, we would use regex, or regular expressions.

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

Since a regex is considered a literal, it is important to wrap it in slashes. Here is an example of what this could look like: 

/^([A-Za-z]|[0-9])+$/

### Anchors

When using regex, we use anchors. The characters for these anchors are the carat (^) and dollar sign ($). These define the start of the string, and the end of the string respectively. There are also bracket expressions which represents the range of characters that the string will match. For example:

[A-Z] from the above code snippet means that the string will be able to match any letter from the alphabet that is capital. It works the same with lowercase and numbers ([0-9]).

### Quantifiers

Quantifiers in regular expressions are special characters or symbols that specify how many times a preceding character, or group, should be repeated for a match to occur. They are fundamental for expressing repetition and specifying patterns. Let's go into more detail as to what they do.

**1. Asterisk (*)**

This quantifier matches a pattern zero or more times.

**2. Plus Sign (+)**

This quantifier matches a pattern one or more times.

**3. Question Mark (?)**

This quantifier matches a pattern zero or one time.

**4. Curly Braces**

This quantifier specifies a number or range of numbers to match to. For example, {n} would match "n" number of times, {n, } would match at least "n" number of times, and {n, m} will match a number "n" to "m" times.

Since we now know what quantifiers do, let's compare it to another example:

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

This code snippet uses the plus sign and curly brace quantifiers. 

When looking at the plus sign, we can see that the first portion of the code ([a-z0-9_\.-]+), which represents the username of an email address, is checking to make sure that this portion of the email address contains one or more valid characters. 

When looking at the curly braces, we can see that the last portion of the code {2,6}, is specifying the pattern for repetition for the class [a-z\.]. It is stating that there must be between 2-6 characters that match the class [a-z\.].

### Grouping Constructs

Grouping constructs are used to group multiple classes into a single snippet. When grouping, you should always enclose your class in parenthesis. In the earlier code snippet, we can see that each part is matching itself to an email address. For example:

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

([a-z0-9_\.-]+) this portion of the code here is checking that the username of the email matches all criteria.

([\da-z\.-]+) this portion is checking that the email website matches all criteria.

And finally, ([a-z\.]{2,6}) is checking that the domain name matches all criteria.

### Bracket Expressions

Bracket expressions, or character classes, are what we use to define set of characters to match our string to. As stated in the earlier examples, [A-Za-z] means that the string must contain capital and lowercase characters from a-z. You may also use numbers (ex: [0-9]).

### The OR Operator

In regular expressions, the OR operator is represented by the pipe (|) character. When using this character, it allows you to specify alternatives within a pattern. Take a look at this:

pattern1|pattern2|pattern3

When looking at the above example, and knowing what we know about the OR operator, we can tell that the pattern will be able to match "pattern1", "pattern2" or "pattern3". It provides more options for matching.

### Character Classes

A character class is used to define a set of characters. We've already discussed many of these in the above examples. One thing to note is that they can be used to both match and exclude characters in your regular expressions.

### Flags

Flags are attributes that can be applied to a regex pattern to modify how it behaves when matching text. Flags can be used to provide more control and customization to the matching. Typically they are added to the end of a pattern such as this: "/pattern/flags". Let's take a quick look at some examples of flags.

Case Insensitivity (i): This flag makes it so that the pattern is case-inensitive, meaning it will match both uppercase and lowercase letters.

Global Matching (g): This flag enables global matching, meaning the pattern will find all matches in the input text, rather than just the first one.

Multi-line Mode (m): This flag is used for multi-line matching. It can change the behavior of anchors and make them match the start and end of each line, rather than the entire text.

These are just some examples of the many types of flags.

### Character Escapes

In regex, character escapes are special sequences of characters that have predefined meanings. They can be used to match specific characters or classes, including those that are considered special by the regex engine. When using character escapes, they shold start with a blackslash (\) followed by one or more characters. Here are some examples of character escapes:

/d: This character escape matches any digit character (0-9). It is essentially the same as the bracket expression [0-9].

/w: This character escape matches any character that is not a word characters. Much like the example above, it is also the same as [A-Za-z]

/S: This character escape matches any character that is not a whitespace character, a whitespace character being spaces, tabs, etc.

## Author


Thanks so much for reading my tutorial! My name is Chelsey Finn and I'm a student at UCF's coding bootcamp full-stack web-development program. If you're interested in what you saw, here's my GitHub profile: https://github.com/cfinn7789