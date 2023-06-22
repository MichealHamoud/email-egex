# Title 
Matching an Email: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

Introductory paragraph (replace this with your text)

## Summary
The Regex I will be breaking down is [ Matching an Email: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ ]`, and about what each 
symbol/character does.
This regular expression matches an email address consisting of a username that can contain lowercase letters, numbers, underscore, dash, or dot, followed by the @ symbol, and a domain name that can include lowercase letters, numbers, dash, dot, or underscore, followed by a dot and a top-level domain that consists of two to six lowercase letters or dots..

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)
- [Example](#example)

## Regex Components
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

### Anchors

In the regular expression `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`, the anchors used are `^` and `$`, just like in the previous explanation. Let's review their significance in this context:
`^` (caret) is the start of line anchor. It indicates that the pattern must start at the beginning of a line or string.
`$` (dollar sign) is the end of line anchor. It specifies that the pattern must occur at the end of a line or string.
The anchors ^ and $ help define the boundaries for matching the email address pattern within the input text and ensure it is not embedded within other content.

### Quantifiers

`+` (plus sign) - This quantifier indicates that the preceding pattern should occur one or more times. It applies to the following parts of the regex:

`([a-z0-9_\.-]+)` - Matches one or more occurrences of lowercase letters, digits, underscores, dots, or hyphens.
`([\da-z\.-]+)` - Matches one or more occurrences of digits, lowercase letters, dots, or hyphens.
`{2,6}` - This quantifier specifies a range of occurrences for the preceding pattern. In this regex, it applies to the following part:

`([a-z\.]{2,6})` - Matches lowercase letters or dots, and requires the length of the matched string to be between 2 and 6 characters.
These quantifiers allow flexibility in matching patterns with varying lengths or multiple occurrences. They play a crucial role in defining the structure and repetition of elements within the regex.

### Grouping Constructs

`([a-z0-9_\.-]+)` - This is the first capturing group. It captures the username portion of the email address. It matches one or more occurrences of lowercase letters, digits, underscores, dots, or hyphens.

`([\da-z\.-]+)` - This is the second capturing group. It captures the domain name portion of the email address. It matches one or more occurrences of digits, lowercase letters, dots, or hyphens.

`([a-z\.]{2,6})` - This is the third capturing group. It captures the top-level domain (TLD) portion of the email address. It matches lowercase letters or dots and requires the length of the matched string to be between 2 and 6 characters.

The grouping constructs are useful for extracting specific parts of the matched text. In programming or regular expression engines, you can access the captured groups separately and utilize the extracted information as needed.

### Bracket Expressions

`[a-z0-9_\.-]` - This bracket expression defines a character class that matches a single character. It includes the following characters:

`a-z` - Matches any lowercase letter from "a" to "z".
`0-9` - Matches any digit from 0 to 9.
`_ `(underscore) - Matches the underscore character.
`\., \.-` - Matches a dot character or a hyphen character.
`[a-z\.]` - This bracket expression defines a character class that matches a single character. It includes the following characters:

`a-z` - Matches any lowercase letter from "a" to "z".
`\.` - Matches a dot character.
These bracket expressions are used within the capturing groups to specify the allowed characters for each part of the email address. They define the range of characters that can be matched within those portions.

It's important to note that the backslashes `(\)` before the dot `(.)` and hyphen `(-)` characters within the bracket expressions are used to escape them so that they are treated as literal characters rather than having their special regex meanings.

These bracket expressions play a role in determining the valid characters for the username, domain name, and top-level domain portions of the email address in the given regular expression.

### Character Classes

`\d` - This character class represents digits from 0 to 9. It is equivalent to the range `[0-9]`. In the regex, it is used within the second capturing group `([\da-z\.-]+)` to match a digit character.

`[a-z]` - This character class represents lowercase letters from "a" to "z". It matches any lowercase letter. It is used in multiple places in the regex:

Within the first capturing group `([a-z0-9_\.-]+)`, it matches lowercase letters in the username portion of the email address.
Within the second capturing group `([\da-z\.-]+)`, it matches lowercase letters in the domain name portion of the email address.
Within the third capturing group `([a-z\.]{2,6})`, it matches lowercase letters in the top-level domain (TLD) portion of the email address.
These character classes provide a concise way to represent sets of characters within a regular expression. They allow you to match specific categories of characters, such as digits or lowercase letters, without having to list each individual character separately.

### The OR Operator

In the regular expression `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`, the OR operator, denoted by the pipe character `(|)`, is not explicitly used. The regex pattern focuses on defining specific character classes, quantifiers, and anchors to match and validate email addresses.

However, it's worth noting that the pipe character can be used in regular expressions to indicate alternative choices or options. It allows you to specify multiple patterns, and the regex engine will match any of them. Here's an example that demonstrates the use of the OR operator with a modified pattern:

`/^(foo|bar|baz)$/`
In this example, the OR operator is used to specify three options: "foo," "bar," or "baz." The regex will match a string that exactly matches one of these options at the beginning `(^)` and end `($)` of the line or string.

Remember, in the provided email regex `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`, the OR operator is not present, but it is a useful tool to handle alternative choices in regular expressions.

### Flags

In the regular expression `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`, there are no flags present at the end of the regex pattern. Flags are optional modifiers that can be appended to a regular expression to change its behavior. They provide additional control over how the regex engine interprets and processes the pattern. Commonly used flags include:

`i` (case-insensitive): When this flag is used, the regex pattern matches regardless of letter case. For example, /pattern/i would match "Pattern," "PATTERN," and "pattern."

`g` (global): This flag enables global searching, allowing the regex engine to find multiple matches within the input text, rather than stopping at the first match.

`m` (multiline): When the multiline flag is used, it changes how the anchors `(^ and $)` behave. They will match the start and end of each line in multiline input, rather than just the start and end of the entire string.

In the provided regex `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`, there are no flags specified. The regex pattern is using the default behavior of the regex engine without any additional modifications.

### Character Escapes

`\.` - This character escape represents a literal dot character `(.)`. It is used in two places:

Within the second capturing group `([\da-z\.-]+)`, it matches a dot character in the domain name portion of the email address.
Within the third capturing group `([a-z\.]{2,6})`, it matches a dot character in the top-level domain (TLD) portion of the email address.
`\-` - This character escape represents a literal hyphen character `(-)`. It is used within the first capturing group `([a-z0-9_\.-]+)` to match a hyphen character in the username portion of the email address.

`\_` - This character escape represents a literal underscore character `(_)`. It is used within the first capturing group `([a-z0-9_\.-]+)` to match an underscore character in the username portion of the email address.

`\d` - This character escape represents a digit character from 0 to 9. It is used within the second capturing group `([\da-z\.-]+)` to match a digit character in the domain name portion of the email address.

These character escapes allow you to match specific characters as literal characters within the regular expression, overriding their special meanings. They are denoted by a backslash `(\)` followed by the character that needs to be escaped.

### Example
Examples of valid email address as per Regex pattern

john.doe@example.com
mary.saunders_123@example.com
Examples of invalid email addresses

John.doe@example.com (as Username cannot have an uppercase alphabet)
john*doe@example.con (as Username cannot have a non-alphanumeric character other than underscore, dash and dot )
john.doe@example_123.co (as Domain name cannot have an underscore)
john.doe@example.c (as Domain extension should have min 2 alphabets)
john.doe@example.com123 (as Domain extension cannot have non alphabet)

## Author
 
https://github.com/MichealHamoud
