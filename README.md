# Regex for Validating Email Addresses

Email validation is a common task in web development, and regular expressions provide an efficient way to accomplish it. This README will explain a regex for validating email addresses using the format `[username]@[domain].[top-level domain]`.

## Summary

The regular expression we will be discussing is `^([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})$`. This regex matches any string that follows the email address format of `[username]@[domain].[top-level domain]`.

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
 Anchors are used to match the position of the regex within the string. The `^` symbol is an anchor that matches the beginning of the string, and the `$` symbol matches the end of the string. In our email regex, we use both of these anchors to ensure that the email address is the only thing in the string. Here's an example of how to use anchors:

```sql
^regex$    // matches the exact string "regex"

^regex     // matches any string that starts with "regex"

regex$     // matches any string that ends with "regex"
```

In our regex,`^([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})$`, we can see that `^` and `$` are being used to indicate a match at the start of the string and the end of the string.
### Quantifiers
Quantifiers are used to specify how many times a character or group of characters should be matched. The `+` symbol is a quantifier that matches one or more of the preceding character or group. In our email regex, we use this quantifier to match one or more of the username and domain name characters. Here's an example of how to use quantifiers:

```sql
a+        // matches one or more "a" characters

ab*       // matches zero or more "b" characters following an "a"

c?        // matches zero or one "c" character

d{10,50}    // matches between 10 and 50 "d" characters
```

In our regex,`^([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})$`, we are using the `+` symbol quantifier that matches one or more occurrences of the preceding character or group.

The `{2,5}` quantifier that matches between 2 and 5 occurrences of the preceding character or group.

### Grouping Constructs
Grouping constructs are used to group parts of the regex together. The `()` symbols are used to create a group, and the `|` symbol is used to match either one group or another. In our email regex, we use grouping constructs to group the username, domain name, and top-level domain name together. Here's an example of how to use grouping constructs:

```sql
(a|b)     // matches either "a" or "b"

(abc)     // matches the exact string "abc"

(abc)+    // matches one or more occurrences of "abc"
```

In our regex,`^([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})$`, we had multiple uses that can be best explained like this:

```sql
([a-zA-Z0-9_\-\.]+)   Creates a capturing group that matches one or more occurrences of any alphanumeric character, underscore, hyphen, or period.

([a-zA-Z0-9_\-\.]+)   Creates another capturing group that matches one or more occurrences of any alphanumeric character, underscore, hyphen, or period.

([a-zA-Z]{2,5})       Creates a third capturing group that matches between 2 and 5 occurrences of any alphabetic character.
```

### Bracket Expressions
Bracket expressions are used to match any one character within a set of characters. The `[]` symbols are used to create a bracket expression. In our email regex, we use bracket expressions to match any one character within the username and domain name. Here's an example of how to use bracket expressions:

```sql
[a-z]     // matches any one lowercase letter

[A-Z]     // matches any one uppercase letter

[0-9]     // matches any one digit

[abc]     // matches any one of the characters "a", "b", or "c"
```

In our regex,`^([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})$`, we had 2 different occurances of bracket expressions.

```sql
[a-zA-Z0-9_\-\.]    Matches any alphanumeric character, underscore, hyphen, or period.
[a-zA-Z]            Matches any alphanumeric character 
```

### Character Classes
Character classes are used to match any one character within a certain category of characters. The \ symbol is used to specify a character class. In our email regex, we use character classes to match any one character within the top-level domain name. Belows are some of the character classes:

```sql
 .     Matches everything except the newline character (\n)

 \d    Matches to any numeric number (= [0-9]).

 \w    Matches any alphanumeric character from the basic Latin alphabet, including the underscore (). (= [A-Za-z0-9]).

 \s    Matches a single whitespace character, including tabs and line breaks
```

In our regex,`^([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})$`, we use `.` to match everything expcept `/.` which is used to match the literal dot character `.` that separates the domain name from the top-level domain (TLD) in an email address.

### Flags
Flags are optional parameters that can be used with regular expressions to change their behavior. There are several different flags, but the most commonly used ones are:

```sql 
g     global flag, which causes the regex to match all occurrences in the input string, not just the first one.

i     case-insensitive flag, which causes the regex to match regardless of whether the letters are uppercase or lowercase.

m     multiline flag, which causes the `^` and `$` anchors to match the start and end of each line, rather than just the start and end of the entire input string.
```

Flags are added to the end of a regex pattern, like so: /pattern/flags.

In our regex expression, it doesn't not contain any flags, so we'll skip this part.

### Character Escapes
Character escapes are used to match special characters in a regex pattern that would otherwise be interpreted as metacharacters. To escape a character, you precede it with a backslash \.

For example, if you wanted to match a literal dot (.), which is normally a metacharacter that matches any character, you would use the regex \., with the backslash escaping the dot.

Here are some common character escapes:

```sql
\.     matches a literal dot (.)

\d     matches any digit character (0-9)

\s     matches any whitespace character (space, tab, newline)

\w     matches any word character (letter, digit, underscore)
```
You can also use character escapes to match specific control characters, such as the tab character (`\t`) or the newline character (`\n`).

In our regex,`^([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})$`, we see character escapes being used and just like character classes, we see the `.` again but accompanied by a backslash meaning that it matches a literal dot `.` like in an email address. 

## Author

This tutorial written by Michael Arasimowicz 💻

Github: @TioMeko

Email: marasimowicz@ymail.com
