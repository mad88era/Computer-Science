# Regex: Explained

Understanding regular expressions, also known as regex, is really important for getting good at finding patterns in programming. This tutorial is all about breaking down a specific regex, so you can understand exactly how it works. We'll go through it step by step, so you can see how each part does its job. Whether you're just starting out or you want to learn more, this tutorial will teach you everything you need to know to use regex in your web development projects. We'll cover everything from creating search patterns to understanding how regex works. Let's jump in and learn about regex together!

## Summary

The regex discussed is aimed at matching phone numbers in the format XXX-XXX-XXXX. It employs capturing groups (\d{3}) to capture three digits, hyphens to match the separators, and back-references (\1, \2, \3) to ensure the repetition of the same format for the entire number. This regex is powerful for accurately extracting phone numbers from text data.

Code example; (\d{3})-(\d{3})-(\d{4})


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
Anchors are like signposts in regex, showing where matches should happen in text. They're different from regular letters because they show positions, not actual characters. The main ones are ^ (caret), which marks the start of a line, and $ (dollar sign), which marks the end. Anchors are important for making sure certain patterns are at the start or end of a string.

Examples:

^: Matches the start of a line.
$: Matches the end of a line.
Regex: ^Hello

Description: This regex looks for the word "Hello", but only if it's right at the beginning of a line.

### Quantifiers
Quantifiers are like controllers in regular expressions that decide how many times a character or group should repeat in a pattern. They help create flexible and accurate search rules.

Examples:

*: Matches zero or more of the previous element.

+: Matches one or more of the previous element.

?: Matches zero or one of the previous element.

{n}: Matches exactly n of the previous element.

{n,}: Matches at least n of the previous element.

{n,m}: Matches between n and m of the previous element.

Regex: a+

Description: This regex finds one or more occurrences of the letter "a" in the text. For example, it matches "a", "aa", "aaa", and so on.

### OR Operator
The OR operator in regex, shown as |, lets you offer choices within a pattern. It matches either the part before it or the part after it. For instance, cat|dog would match either "cat" or "dog". This operator helps create patterns that can find different versions of a specific word or phrase.

Example:

|: Matches either the part before or after it.
Regex: cat|dog

Description: This regex successfully finds either "cat" or "dog" in the text.

### Character Classes
Character classes in regular expressions let you define a group of characters that can fit into a particular spot within the pattern. These classes are written inside square brackets [ ]. For example, [aeiou] matches any vowel, and [0-9] matches any digit. Using character classes helps make patterns that can match different characters at a specific position.

Example:

[aeiou]: Matches any vowel.
[0-9]: Matches any digit.
[a-zA-Z]: Matches any letter (both lowercase and uppercase).
Regex: [aeiou]

Description: This regex successfully finds any vowel character in the text.

### Flags
Flags, also called modifiers, are extra settings you can add to a regex pattern to change how it works. They tell the regex engine how to understand the pattern. Some common flags include:

i: Makes matching case-insensitive.
g: Finds all matches instead of just the first one.
m: Changes how ^ and $ work to match the start and end of lines instead of the whole string.
Example:

i: Case-insensitive matching.
g: Global matching (finding all matches instead of just the first one).
m: Multiline mode (changing how ^ and $ work).
Regex: /hello/i

Description: This regex finds "hello" in the text without caring about uppercase or lowercase.

### Grouping and Capturing

Grouping in regex lets you bundle characters together using parentheses (). These groups, called capturing groups, not only organize the regex but also store the matched text for future use. Understanding how to group and capture text is crucial for isolating specific parts of a match or making changes to matched text.

Example:

(): Creates a capturing group.
Regex: (\d{3})-(\d{3})-(\d{4})
Description: This regex captures phone numbers in the format XXX-XXX-XXXX.
### Bracket Expressions

Bracket expressions, or character classes, match any single character inside square brackets [ ]. They're handy for defining sets of characters that can match at a specific spot in the pattern. This flexibility helps craft patterns that can match various characters or character ranges.

Example:

[abc]: Matches any of the characters inside the brackets.
Regex: [abc]
Description: This regex matches any of the characters 'a', 'b', or 'c' in the text.

### Greedy and Lazy Match

Greedy and lazy quantifiers (like *, +, and ?) dictate how much text a quantified expression should match. Greedy quantifiers aim to match as much text as possible, while lazy quantifiers aim for the least. Understanding this difference is key for fine-tuning regex patterns and avoiding unintended matches.

Example:

(greedy): Matches as much text as possible.
*? (lazy): Matches as little text as possible.
Text: <p>Hello</p><p>World</p>
Regex: <p>.*
Description: This greedy regex matches <p>Hello</p><p>World</p> in the text.

### Boundaries

Boundaries (like \b for word boundaries and \B for non-word boundaries) mark positions where specific conditions are met in the text. They help define precise search criteria by identifying word or non-word positions.

Examples:

\b: Matches a word boundary.
\B: Matches a non-word boundary.
Regex: \bcat\b
Description: This regex matches "cat" as a whole word in the text.

### Back-references

Back-references allow you to reuse previously matched text stored in capturing groups. They're represented by \1, \2, etc., where the number corresponds to the index of the capturing group. Utilizing back-references enhances regex patterns by enabling advanced matching and substitution techniques.

Examples:

\1, \2, etc.: Refers back to the contents of capturing groups.
Regex: (\d{3})-(\d{3})-(\d{4}) \1-\2-\3
Description: This regex matches a phone number followed by the same phone number again (e.g., 123-456-7890 123-456-7890).

### Look-ahead and Look-behind

Look-ahead and look-behind assertions verify whether a specific pattern is or isn't followed by or preceded by another pattern without including the matched text in the overall match result. Positive assertions are represented by (?=...), (?<=...), while negative assertions are represented by (?!...) and (?<!...). Mastering look-ahead and look-behind enhances regex capabilities for addressing complex matching criteria.

Example:

(?=...): Positive look-ahead assertion.
(?<=...): Positive look-behind assertion.
(?!...): Negative look-ahead assertion.
(?<!...): Negative look-behind assertion.
Regex: (?<=\d{3}-)\d{3}-\d{4}
Description: This regex matches a phone number preceded by another phone number in the format XXX-XXX-XXXX.

## Author

About the Author:
Ismael Madera is a beginner web developer who's excitedly starting his adventure in regex and pattern matching. He's eager to learn and has a fresh outlook on diving into the world of regex. For more of Ismael's projects and contributions, you can visit his GitHub profile: Mad88era.







