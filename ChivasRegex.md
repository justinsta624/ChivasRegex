# ChivasRegex: Tutorial on Matching a URL

Regular expressions, commonly referred to as Regex, constitute a highly valuable and potent tool for extracting information from textual sources, encompassing code, log files, spreadsheets, and documents. Among the myriad applications, a prevalent use case involves the validation and matching of Uniform Resource Locators (URLs).

This tutorial will provide comprehensive guidance on employing Regex to ascertain the adherence of a given string to the standardized URL format.

## Summary

Within this document, I will elucidate the utilization of a regular expression designed to validate URLs, guaranteeing adherence to a specific pattern:

```regex
/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/
```

While the sequence of characters may appear cryptic at first glance, it represents a structured assembly of regular expression components, each of which will be thoroughly explored in the subsequent discussion.

Let us delve into the intricacies of each Regex Component, elucidating the process of constructing a robust URL matching pattern using the content provided in this document.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Lazy and Greedy Match](#lazy-and-greedy-match)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Boundaries](#boundaries)
- [Back-references](#back-references)

## Regex Components

Initiating the creation of a series of expressions requires commencing with a `/` and concluding at the end of the string. For instance:

`/ChivasRegex/`

### Anchors

The characters `^` and `$` function as anchors, employed to match the start and end of a string, respectively.

### Boundaries

In regex, boundaries are used to define the start and end points of a match within a string. The anchors `^` and `$` are commonly used for this purpose.

```regex 
/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/
```

- `^` asserts the start of the string, ensuring that the URL begins as intended.
- `$` asserts the end of the string, ensuring that the URL concludes according to the specified pattern.
These boundaries help to validate the entire string against the defined URL structure.

### Quantifiers

Quantifiers permit the specification of how frequently a particular regex string should match. Two variants exist: lazy and greedy. By default, regex matching is eager, seeking to match as much as possible. This behavior may not always be desired. Lazy quantifiers restrict the matched content. Quantifiers include:

- `+` matches the pattern one or more times.
- `*` matches the pattern zero or more times.
- `?` matches the pattern zero or one time.
- `{}` curly brackets establish limits for a match:
    - `{n}` matches the pattern exactly n times.
    - `{n,}` matches the pattern at least n times.
    - `{n,x}` matches the pattern from a minimum of n times to a maximum of x times.

Breakdown of the provided regex:

- `(https?:\/\/)?` is an optional group, allowing for either "http://" or "https://".
- `([\da-z\.-]+)` captures the domain name, permitting alphanumeric characters, dots, or hyphens.
- `\.([a-z\.]{2,6})` matches the top-level domain (TLD), consisting of two to six lowercase letters or dots.
- `([\/\w \.-]*)*` captures optional path segments, query parameters, or fragments, allowing any character from the set [/, \w (alphanumeric), space, dot, hyphen].
- `\/?` matches an optional trailing slash.

### Lazy and Greedy Match

```Lazy Quantifiers
([\/\w \.-]*?)*
```
This change makes the quantifier match as little as possible, ensuring it captures the smallest valid portion. In the context of URLs, this can be useful when you want to match the shortest possible path segment or query parameter.


```Greedy Quantifiers
([\/\w \.-]*)*
```
The `*` quantifier is used to match zero or more occurrences of the characters within the character class. It is greedy by default, meaning it will try to match as many characters as possible. In the context of URLs, this allows flexibility in capturing path segments, query parameters, or fragments.

### OR Operator

The OR operator, denoted by the vertical bar `|`, specifies alternatives within a pattern, allowing the matching of one pattern or another.

```regex
(https?:\/\/)?
```
The question mark `?` after the group indicates that the entire group `(https?:\/\/)` is optional. This group captures the scheme part of the URL, allowing for either `"https://"`. It effectively functions as an OR operator, indicating that the URL may start with `"https://"`, or it may start with nothing at all.

```regex
\.([a-z\.]{2,6})
```
This group allows for two to six lowercase letters or dots. It serves as a simplified representation of various TLD (Top-Level Domain) possibilities. The dot before the character class `([a-z\.])` indicates the OR operator, allowing for either a dot or a lowercase letter.

### Character Classes

Character classes(escape) in regex allow the literal matching of specific characters, bypassing their special meanings. Common examples include:

  - `\.` (Escapes the dot `(.)` character) - it matches a literal dot instead of its special meaning, which is to match any character (except newline) in regular expressions.

  - `\/` (Escapes the forward slash `(/)` character) - it matches a literal forward slash instead of its special meaning, which is often used as a delimiter in regular expressions.

  - `\\` (Escapes the backslash `(\)` character) -  it matches a literal backslash instead of its special meaning as an escape character.

  - `\+, \-, \*, etc.` (Escapes special characters like `+`, `-`, `*`, `etc.`) - it is to match them literally instead of their special meanings in regular expressions.

  - `\d, \w, \s` These are shorthand character classes that match digits `(\d)`, word characters `(\w)`, and whitespace characters `(\s)`, respectively. They are used as escapes to represent these predefined character classes.

Using character classes(escape) enables the precise matching of characters without interpreting their special meanings within the regex syntax.

### Flags

Flags, optional parameters appended to the regex, modify pattern matching behavior, altering how the pattern is interpreted or applied. They are appended to the end of the regex and are usually represented by a single letter. 

- `i` (Case-Insensitive):
`/regex/i`
This flag makes the pattern case-insensitive, allowing it to match uppercase and lowercase letters interchangeably. For example, `/abc/i` would match "abc", "AbC", "aBC", etc.

- `g` (Global Match):
`/regex/g`
This flag enables global matching, meaning the regex will find all matches within the input string rather than stopping after the first match.

- `m` (Multiline):
`/regex/m`
In multiline mode, the `^` and `$` anchors match the start and end of each line within the input string, rather than the start and end of the entire string.

- `u` (Unicode):
`/regex/u`
This flag is used when working with Unicode strings. It ensures that Unicode characters are treated correctly by the regex engine.

- `s` (DotAll):
`/regex/s`
In DotAll mode, the dot `.` in the regex matches any character, including newline characters `(\n)`.

- `x` (Extended):
`/regex/x`
In extended mode, whitespace and comments are ignored within the regex pattern, allowing for a more readable format.

Using the case-insensitive flag `(/regex/i)` to match URLs regardless of case. 
The global match flag `(/regex/g)` to use multiple URLs in the input text.

```regex 
/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/ig
```

### Grouping and Capturing

Grouping and Capturing in regular expressions (denoted by parentheses) amalgamate multiple characters or subpatterns, treating them as a singular unit. The grouped regex looks like:
```regex
(https?:\/\/) ([\da-z\.-]+) ([a-z\.]{2,6}) ([\/\w \.-]*)
```

### Bracket Expressions

Bracket expressions, or character classes, enable the definition of a set or range of characters for matching against a single character position. They are denoted by square brackets `[ ]`. Examples include:

- `[abc]`: Matches either "a", "b", or "c".
- `[0-9]`: Matches any digit from 0 to 9.
- `[a-z]`: Matches any lowercase letter from "a" to "z".
- `[A-Z]`: Matches any uppercase letter from "A" to "Z".
- `[0-9a-fA-F]`: Matches any hexadecimal digit.

A few special characters have special meanings within brackets include:

- Hyphen `(-)`: Specifies a character range. For example, `[a-z]` matches any lowercase letter.
- Caret `(^)`: When used as the first character inside the brackets, it negates the character set. For example, `[^0-9]` matches any character that is not a digit.
- Backslash `(\)`: Escapes a special character inside the bracket expression.

The grouped regex for the provided example:
```regex 
  [\da-z\.-] [a-z\.] {2,6} [\/\w \.-]
```

### Back-references

Back-references in regex allow referencing previously captured groups within the pattern. They are denoted by \ followed by the group number. However, the provided URL regex doesn't utilize back-references.

For example, a back-reference could be used to ensure that the opening and closing tags in an HTML document match:

```regex 
<(div|p)>(.*?)<\/\1>
```
In this case, `\1` references the first captured group `(div|p)`.

## Author

Copyright (c) 2024 Hanbyeol Lee

Hanbyeol Justin Lee, with my [GitHub](https://github.com/justinsta624), is currently pursuing a Coding Bootcamp program at the University of Toronto. 

I am independently motivated, also appreciate team efforts and collaborate productively within teams. I understand exactly and accurately to help solve issues to prevent wasting time. I depend on accurate data, correct information, and precise numbers.

With years of doing research, presentations and using technology in school and at work, MS office as Excel, PowerPoint, Word, Sharepoint, Teams and Outlook are essential in my toolbox. I'm about to include various coding skills by using various of front & back-ends to perform my tasks, pursuing significant career transition into the Web Development Industry.