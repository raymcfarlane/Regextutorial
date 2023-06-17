# Regex-Tutorial
- Gist link (https://gist.github.com/raymcfarlane/def885cc6cbad5e788c22565dbb88611)

A **regex**, which is short for **regular expression**, is a sequence of characters that defines a specific search pattern. When included in code or search algorithms, regular expressions can be used to find certain patterns of characters within a string, or to find and replace a character or sequence of characters within a string. They are also frequently used to validate input. 

## Summary

I will be explaining a regular expression, **"Matching a username"**
```
/^[a-z0-9_-]{3,16}$/
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

A regex is considered a literal, so the pattern must be wrapped in slash characters (/). 

### Anchors

The characters ^ and $ are both considered to be anchors.
The ^ anchor signifies a string that begins with the characters that follow it. This could be in one of two formats:
An exact string match, such as ^The, where the strings "The" or "The person" match, but "the" and "the person" do not. This is because a regex is case-sensitive.
A range of possible matches, displayed using bracket expressions.
The $ anchor signifies a string that ends with the characters that precede it. Just as with the ^ character, it can be preceded by an exact string or a range of possible matches.

### Quantifiers

Quantifiers set the limits of the string that your regex matches (or an individual section of the string). They frequently include the minimum and maximum number of characters that your regex is looking for.

For "Matching a Username” regex there are quantifier {3,16}. This means that we want to find the preceding string pattern a minimum of 3 times and a maximum of 16 times. Because our bracket expression ([a-z0-9_-]) will match any string that includes any combination of lowercase letters between a and z, any number between 0 and 9, and the special characters of an underscore or a hyphen, this quantifier means that this string has to be between 3 and 16 characters.

### Grouping Constructs

The “Matching a Username” regex is fairly straightforward and open-ended about what it accepts. As regular expressions grow more complicated, you may check multiple parts of a string to determine that different sections fulfill different requirements. To break these sections up, you'll need to use grouping constructs.
The primary way you group a section of a regex is by using parentheses (()). Each section within parentheses is known as a subexpression. Grouping constructs have two primary categories: capturing and non-capturing.

### Bracket Expressions

Anything inside a set of square brackets ([]) represents a range of characters that we want to match. These patterns are known as bracket expressions.

In our example of "Matching a username"
[a-z]—The string can contain any lowercase letter between a–z.If we wanted to include uppercase characters, we would need to change the expression to [a-zA-Z].
[0-9]—The string can contain any number between 0–9
[_-]—The string can contain an underscore or hyphen. Both the underscore and the hyphen are called special characters.

### Character Classes

A character class in a regex defines a set of characters, any one of which can occur in an input string to fulfill a match. 
Some of the other common character classes:.—Matches any character except the newline character (\n), \d—Matches any Arabic numeral digit. This class is equivalent to the bracket expression [0-9].\w—Matches any alphanumeric character from the basic Latin alphabet, including the underscore (_). This class is equivalent to the bracket expression [A-Za-z0-9_].\s—Matches a single whitespace character, including tabs and line breaks

### The OR Operator

Bracket expression does not require the string to meet all of the requirements in the pattern. This means that [a-z0-9_-] searches for alphanumeric characters or the two special characters included in the pattern. Often, you'll want to add this same logic outside of a bracket expression, especially within a grouping construct or between two different grouping constructs. Using the OR operator (|), the expression [abc] could be written as (a|b|c).

Here is an example of the **OR operator**:(a|b|c):(x|y|z)

### Flags

A regex must be wrapped in slash characters. The one exception to this rule is with the component known as flags. Flags are placed at the end of a regex, after the second slash, and they define additional functionality or limits for the regex. 

There are six optional flags that can be used, either separately or together and in any order, but these are the three you're most likely to encounter: g—Global search: the regex should be tested against all possible matches in a string. i—Case-insensitive search: case should be ignored while attempting a match in a string. m—Multi-line search: a multi-line input string should be treated as multiple lines

### Character Escapes

The backslash (\) in a regex escapes a character that otherwise would be interpreted literally. For example, the open curly brace ({) is used to begin a quantifier, but adding a backslash before the open curly brace (\{) means that the regex should look for the open curly brace character instead of beginning to define a quantifier. This is common when looking for strings with special characters that are the same as a particular component of a regex.

## Author

Raynica McFarlane- UNCC Full-Stack Coding Bootcamp student

GitHub profile (https://github.com/raymcfarlane)

 
