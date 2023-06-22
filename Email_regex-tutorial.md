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
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)
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

### Grouping and Capturing

`([a-z0-9_\.-]+)` - This is the first capturing group. It captures the username portion of the email address. It matches one or more occurrences of lowercase letters, digits, underscores, dots, or hyphens.

`([\da-z\.-]+)` - This is the second capturing group. It captures the domain name portion of the email address. It matches one or more occurrences of digits, lowercase letters, dots, or hyphens.

`([a-z\.]{2,6})` - This is the third capturing group. It captures the top-level domain (TLD) portion of the email address. It matches lowercase letters or dots and requires the length of the matched string to be between 2 and 6 characters.

The capturing groups are enclosed in parentheses and allow you to capture and extract specific portions of the matched text. When a match is found, the captured content within the groups can be accessed separately. The order of capturing groups corresponds to the order of their appearance in the regex pattern.

For example, when applying the regex to the string "john.doe@example.com," the first capturing group captures "john.doe," the second capturing group captures "example," and the third capturing group captures "com."

### Greedy and Lazy Match

Greedy Matching: By default, quantifiers are greedy, meaning they match as much text as possible while still allowing the overall pattern to match. The quantifiers `+` (one or more) and `*` (zero or more) are greedy by default. For example:

`.*` (dot-star) matches any sequence of characters, including the maximum possible number of characters.
Lazy (Non-greedy) Matching: In contrast, lazy or non-greedy matching matches as little text as possible while still allowing the overall pattern to match. The `?` quantifier makes the preceding pattern lazy. For example:

`.*?` matches any sequence of characters, but it stops at the first possible match of the subsequent pattern.
Lazy matching is useful when you want to match the shortest possible string that satisfies the pattern. It is commonly used when there is a need to match text within a specific context or when you want to minimize the amount of text captured.

In the provided regular expression `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`, there are no explicit use of lazy matching. The quantifiers `+` and `{2,6}` are greedy by default. However, it's worth noting that the use of lazy quantifiers may vary depending on the specific requirements of your regex pattern and the regular expression engine you are using.

### Boundaries

In regular expressions, boundaries are used to define specific positions within the input text. They allow you to match patterns that occur at certain positions relative to other characters or boundaries. The most commonly used boundaries are:

`^ `(caret) - The caret represents the start of a line or string. When placed at the beginning of a regular expression pattern, it matches the position at the start of the input text.

`$` (dollar sign) - The dollar sign represents the end of a line or string. When placed at the end of a regular expression pattern, it matches the position at the end of the input text.

These boundaries help you define patterns that need to match at the beginning or end of a line or string. For example:

`/^Hello/` matches "Hello" only if it appears at the start of a line or string.
`/world$/` matches "world" only if it appears at the end of a line or string.
In the provided regular expression `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`, the `^` and `$` symbols are used as boundaries. They indicate that the entire email address should match from the start `(^)` to the end `($)` of the line or string. This ensures that the regular expression pattern matches the entire email address and doesn't allow any additional characters before or after it.

### Back-references

In regular expressions, back-references are used to refer back to previously matched groups within the pattern. They allow you to match the same text that was previously captured by a capturing group and use it later in the pattern. Back-references are typically indicated by `\` followed by a digit.

Here's an example to illustrate the use of back-references:

Consider the regular expression pattern `(\w)\1`. In this pattern, `(\w)` is a capturing group that matches a single word character. The `\1` is a back-reference that matches the same text that was captured by the first capturing group.

So, if the input text is "hello," the pattern will match the repeating "ll" because the first capturing group captured the letter "l" and the back-reference `\1` matches the same "l" again.

Back-references are useful when you want to ensure that the same text is repeated or when you need to check for repeated sequences within the input text.

In the provided regular expression `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`, there are no explicit back-references used. The capturing groups in the pattern capture specific portions of the email address, but they are not referred to later in the pattern using back-references.

### Look-ahead and Look-behind

Look-ahead and look-behind are zero-width assertions in regular expressions that allow you to specify conditions that must be met ahead or behind the current position in the input text without including them in the actual match. They are used to enforce certain conditions without consuming the characters that match the condition.

Positive Look-ahead `((?=...)):` Positive look-ahead asserts that the pattern inside the lookahead must be matched at the current position in the input text, without including it in the overall match. It ensures that the pattern is followed by the specified condition. For example, `/foo(?=bar)/` matches "foo" only if it is immediately followed by "bar."

Negative Look-ahead `((?!...)):` Negative look-ahead asserts that the pattern inside the lookahead must not be matched at the current position in the input text. It ensures that the pattern is not followed by the specified condition. For example, `/foo(?!bar)/` matches "foo" only if it is not immediately followed by "bar."

Positive Look-behind `((?<=...)):` Positive look-behind asserts that the pattern inside the lookbehind must be matched immediately before the current position in the input text, without including it in the overall match. It ensures that the pattern is preceded by the specified condition. However, it is important to note that lookbehinds have certain limitations in terms of their length and form in different regex engines.

Negative Look-behind `((?<!...)):` Negative look-behind asserts that the pattern inside the lookbehind must not be matched immediately before the current position in the input text. It ensures that the pattern is not preceded by the specified condition.

Look-ahead and look-behind assertions are powerful tools for adding conditions to your regular expressions without actually including them in the matched text. They are useful for enforcing certain patterns in specific contexts.

In the provided regular expression `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`, there are no explicit look-ahead or look-behind assertions used. The pattern focuses on capturing specific parts of the email address and does not rely on conditions ahead or behind the captured text.

### Example
Examples of valid email addresses
1. john.doe@example.com
2. mary.saunders_123@example.com

Examples of invalid email addresses

1. John.doe@example.com (as Username cannot have an uppercase alphabet)
2. john*doe@example.con (as Username cannot have a non-alphanumeric character other than underscore, dash and dot )
3. john.doe@example_123.co (as Domain name cannot have an underscore)
4. john.doe@example.c (as Domain extension should have min 2 alphabets)
5. john.doe@example.com123 (as Domain extension cannot have non alphabet)

## Author
 
https://github.com/MichealHamoud
