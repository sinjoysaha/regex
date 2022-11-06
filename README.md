# REGular EXpressions from [HackerRank](https://www.hackerrank.com/domains/regex) (with Solutions in Python 3)

[![GitHub contributors](https://img.shields.io/github/contributors/sinjoysaha/regex.svg)](https://GitHub.com/sinjoysaha/regex/graphs/contributors/)
[![GitHub forks](https://img.shields.io/github/forks/sinjoysaha/regex.svg)](https://GitHub.com/sinjoysaha/regex/network/)
[![GitHub stars](https://img.shields.io/github/stars/sinjoysaha/regex.svg)](https://GitHub.com/sinjoysaha/regex/stargazers/)
[![GitHub watchers](https://img.shields.io/github/watchers/sinjoysaha/regex.svg)](https://GitHub.com/sinjoysaha/regex/watchers/)
[![GitHub issues](https://img.shields.io/github/issues/sinjoysaha/regex.svg)](https://GitHub.com/sinjoysaha/regex/issues/)
[![Profile views](https://gpvc.arturio.dev/sinjoysaha)](https://GitHub.com/sinjoysaha/)
[![GitHub followers](https://img.shields.io/github/followers/sinjoysaha.svg)](https://github.com/sinjoysaha?tab=followers)
[![LinkedIn](https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&color=545454)](https://linkedin.com/in/sinjoysaha)
[![Twitter](https://img.shields.io/badge/-Twitter-blue.svg?style=flat-square&logo=twitter&color=b3e0ff)](https://twitter.com/SinjoySaha)

`Highlighted` part in the Test String is matched with regex pattern.

## [Introduction](https://www.hackerrank.com/domains/regex?filters%5Bsubdomains%5D%5B%5D=re-introduction)
### 1. [Matching Specific String](https://www.hackerrank.com/challenges/matching-specific-string/problem)
Regex Pattern - wikipedia

Test String - https://en. `wikipedia` .org/
```python
Regex_Pattern = r'hackerrank'	# Do not delete 'r'.

import re
Test_String = input()
match = re.findall(Regex_Pattern, Test_String)
print("Number of matches :", len(match))
```

### 2. [Matching Anything But a Newline](https://www.hackerrank.com/challenges/matching-anything-but-new-line/problem)
dot - The dot (.) matches anything (except for a newline).

Regex Pattern - A.B.C.D.

Test String - `A+B+C=DE`

```
regex_pattern = r"^...\....\....\....$"	# Do not delete 'r'.

import re
import sys
test_string = input()
match = re.match(regex_pattern, test_string) is not None
print(str(match).lower())
```

### 3. [Matching Digits & Non-Digit Characters](https://www.hackerrank.com/challenges/matching-digits-non-digit-character/problem)
\d - The expression \d matches any digit [0-9].

\D - The expression \D matches any character that is not a digit.

Regex Pattern - \D\D\D\D

Test String - `Hack`101
```
Regex_Pattern = r"\d\d\D\d\d\D\d\d\d\d"	# Do not delete 'r'.

import re
print(str(bool(re.search(Regex_Pattern, input()))).lower())
```

### 4. [Matching Whitespace & Non-Whitespace Character](https://www.hackerrank.com/challenges/matching-whitespace-non-whitespace-character/problem)
\s - \s matches any whitespace character [ \r\n\t\f ].

\S - \S matches any non-white space character.

Regex Pattern - \s

Test String - A` `B
```
Regex_Pattern = r"\S\S\s\S\S\s\S\S"	# Do not delete 'r'.

import re
print(str(bool(re.search(Regex_Pattern, input()))).lower())
```

### 5. [Matching Whitespace & Non-Whitespace Character](https://www.hackerrank.com/challenges/matching-whitespace-non-whitespace-character/problem)
\w - The expression \w will match any word character. Word characters include alphanumeric characters (a-z, A-Z and 0-9) and underscores ( _ ).

\W - \W matches any non-word character.
Non-word characters include characters other than alphanumeric characters (a-z, A-Z and 0-9) and underscore ( _ ).

Regex Pattern - \w\w\w

Test String - $`one`
```
Regex_Pattern = r"\w\w\w\W\w\w\w\w\w\w\w\w\w\w\W\w\w\w"	# Do not delete 'r'.

import re
print(str(bool(re.search(Regex_Pattern, input()))).lower())
```

### 6. [Matching Start & End](https://www.hackerrank.com/challenges/matching-start-end/problem)
^ - The ^ symbol matches the position at the start of a string.

$ - The $ symbol matches the position at the end of a string.

Non-word characters include characters other than alphanumeric characters (a-z, A-Z and 0-9) and underscore ( _ ).

Regex Pattern - ^123

Test String - `123`456
```
Regex_Pattern = r"^\d\w\w\w\w.$"	# Do not delete 'r'.

import re
print(str(bool(re.search(Regex_Pattern, input()))).lower())
```

## [Character Class](https://www.hackerrank.com/domains/regex?filters%5Bsubdomains%5D%5B%5D=re-character-class)
### 1. [Matching Specific Characters](https://www.hackerrank.com/challenges/matching-specific-characters/problem)
\[\] - The character class \[\] matches only one out of several characters placed inside the square brackets.

Regex Pattern - \[aeiou\] is a vowel

Test String - `o is a vowel` |  `e is a vowel`
```
Regex_Pattern = r'^[123][120][xs0][30Aa][xsu][.,]$'	# Do not delete 'r'.

import re
print(str(bool(re.search(Regex_Pattern, input()))).lower())
```

### 2. [Excluding Specific Characters](https://www.hackerrank.com/challenges/excluding-specific-characters/problem)
\[^\] - The negated character class \[^\] matches any character that is not in the square brackets.

Regex Pattern - \[^aeiou\] is not a vowel

Test String - `k is a vowel` |  `p is a vowel`
```
Regex_Pattern = r'^[\D][^aeiou][^bcDF][\S][^AEIOU][^.,]$'  # OR r'^[^\d][^aeiou][^bcDF][^\s][^AEIOU][^.,]$'	# Do not delete 'r'.

import re
print(str(bool(re.search(Regex_Pattern, input()))).lower())
```

### 3. [Matching Character Ranges](https://www.hackerrank.com/challenges/matching-range-of-characters/problem)
A hyphen (-) inside a character class specifies a range of characters where the left and right operands are the respective lower and upper bounds of the range. For example:

- \[a-z\] is the same as \[abcde...wxyz\].
- \[A-Z\] is the same as \[ABCDE...WXYZ\].
- \[0-9\] is the same as \[0123456789\].
In addition, if you use a caret (^) as the first character inside a character class, it will match anything that is not in that range. For example,  matches any character that is not a digit in the inclusive range from  to . **It's important to note that, when used outside of (immediately preceding) a character or character class, the caret matches the first character in the string against that character or set of characters.**

Regex Pattern - \[x-z\]\[4-8\]\[A-K\]

Test String - `x5F`
```
Regex_Pattern = r'^[a-z][1-9][^a-z][^A-Z][A-Z]'	# Do not delete 'r'.

import re
print(str(bool(re.search(Regex_Pattern, input()))).lower())
```

## [Repetitions](https://www.hackerrank.com/domains/regex?filters%5Bsubdomains%5D%5B%5D=re-repetitions)
### 1. [Matching {x} Repetitions](https://www.hackerrank.com/challenges/matching-x-repetitions/problem)
{x} - The tool {x} will match exactly  repetitions of character/character class/groups.

Regex Pattern - \w{4}

Test String - `H_ck`
```
Regex_Pattern = r'^[a-zA-Z02468]{40}[13579\s]{5}$'	# Do not delete 'r'.

import re
print(str(bool(re.search(Regex_Pattern, input()))).lower())
```

### 2. [Matching {x, y} Repetitions](https://www.hackerrank.com/challenges/matching-x-y-repetitions/problem)
{x,y} - The {x,y} tool will match between  and  (both inclusive) repetitions of character/character class/group.

Regex Pattern - \w{1,4}\d{4,}

Test String - `Hk132156545654654654` | `Hack1021`
```
Regex_Pattern = r'^\d{1,2}[a-zA-Z]{3,}\.{0,3}$'	# Do not delete 'r'.

import re
print(str(bool(re.search(Regex_Pattern, input()))).lower())
```

### 3. [Matching Zero Or More Repetitions](https://www.hackerrank.com/challenges/matching-zero-or-more-repetitions/problem)
\* - The * tool will match zero or more repetitions of character/character class/group.

Regex Pattern - Ab*s

Test String - `As` | `Abbbbbs`
```
Regex_Pattern = r'^\d{2,}[a-z]*[A-Z]*$'	# Do not delete 'r'.

import re
print(str(bool(re.search(Regex_Pattern, input()))).lower())
```

### 4. [Matching One Or More Repetitions](https://www.hackerrank.com/challenges/matching-one-or-more-repititions/problem)
\+ - The + tool will match one or more repetitions of character/character class/group.

Regex Pattern - Ab+s

Test String - As | `Abbbbbs`
```
Regex_Pattern = r'^\d+[A-Z]+[a-z]+$'	# Do not delete 'r'.

import re
print(str(bool(re.search(Regex_Pattern, input()))).lower())
```

### 5. [Matching Ending Items](https://www.hackerrank.com/challenges/matching-ending-items/problem)
$ - The $ boundary matcher matches an occurrence of a character/character class/group at the end of a line.

Regex Pattern - \w*s$

Test String - `Challenges` | `Hints`
```
Regex_Pattern = r'^[a-zA-Z]*[sS]$'	# Do not delete 'r'.

import re
print(str(bool(re.search(Regex_Pattern, input()))).lower())
```

## [Grouping and Capturing](https://www.hackerrank.com/domains/regex?filters%5Bsubdomains%5D%5B%5D=grouping-and-capturing)
### 1. [Matching Word Boundaries](https://www.hackerrank.com/challenges/matching-word-boundaries/problem)
\\b - \\b assert position at a word boundary.

Regex Pattern - \\bcat\\b

Test String - Acat | A `cat`
```
Regex_Pattern = r'\b[aeiouAEIOU][a-zA-Z]*\b'	# Do not delete 'r'.

import re
print(str(bool(re.search(Regex_Pattern, input()))).lower())
```

### 2. [Capturing & Non-Capturing Groups](https://www.hackerrank.com/challenges/capturing-non-capturing-groups/problem)
\(\) - Parenthesis \(\) around a regular expression can group that part of regex together. This allows us to apply different quantifiers to that group. 

These parenthesis also create a numbered capturing. It stores the part of string matched by the part of regex inside parentheses.

These numbered capturing can be used for backreferences.

Regex Pattern - It is (not)? your fault

Test String - `It is not your fault` | `It is your fault`
```
Regex_Pattern = r'(ok){3,}'	# Do not delete 'r'.

import re
print(str(bool(re.search(Regex_Pattern, input()))).lower())
```

### 3. [Alternative Matching](https://www.hackerrank.com/challenges/alternative-matching/problem)
| - Alternations, denoted by the | character, match a single item out of several possible items separated by the vertical bar. When used inside a character class, it will match characters; when used inside a group, it will match entire expressions (i.e., everything to the left or everything to the right of the vertical bar). We must use parentheses to limit the use of alternations.

Regex Pattern - (and|AND|And)

Test String - `And` the award goes to A `and ` D company
```
Regex_Pattern = r'^(Mr\.|Mrs\.|Ms\.|Dr\.|Er\.)[a-zA-Z]+$'	# Do not delete 'r'.

import re
print(str(bool(re.search(Regex_Pattern, input()))).lower())
```

## [Backreferences](https://www.hackerrank.com/domains/regex?filters%5Bsubdomains%5D%5B%5D=backreferences)
### 1. [Matching Same Text Again & Again](https://www.hackerrank.com/challenges/matching-same-text-again-again/problem)
\\group_number - This tool (\\1 references the first capturing group) matches the same text as previously matched by the capturing group.

Regex Pattern - (\\w)(\\w)(\\w)(\\w)y\\4\\3\\2\\1

Test String - `malayalam`
```
Regex_Pattern = r'^([a-z])(\w)(\s)(\W)(\d)(\D)([A-Z])([a-zA-Z])([aeiouAEIOU])(\S)\1\2\3\4\5\6\7\8\9\10$'	# Do not delete 'r'.

import re
print(str(bool(re.search(Regex_Pattern, input()))).lower())
```

### 2. [Backreferences To Failed Groups](https://www.hackerrank.com/challenges/backreferences-to-failed-groups/problem)
Backreference to a capturing group that match nothing is different from backreference to a capturing group that did not participate in the match at all.

Capturing group that match nothing

Regex Pattern - (\b?)o\\1

Test String - `o`

Here, \b? is optional and matches nothing.
Thus, (\b?) is successfully matched and capture nothing.
o is matched with o and \1 successfully matches the nothing captured by the group.

Capturing group that didn't participate in the match at all

Regex Pattern - (\b)?o\\1

Test String - o

In most regex flavors (excluding JavaScript), (b)?o\1 fails to match o.
Here, (\b) fails to match at all. Since, the whole group is optional the regex engine does proceed to match o.
The regex engine now arrives at \1 which references a group that did not participate in the match attempt at all.
Thus, the backreference fails to match at all.

```
Regex_Pattern = r"^(\d\d)(-?)(\d\d)\2(\d\d)\2(\d\d)$"	# Do not delete 'r'.

import re
print(str(bool(re.search(Regex_Pattern, input()))).lower())
```

### 3. [Branch Reset Groups](https://www.hackerrank.com/challenges/branch-reset-groups/problem)

**NOTE** - Branch reset group is supported by Perl, PHP, Delphi and R.

(?|regex) - A branch reset group consists of alternations and capturing groups. (?|(regex1)|(regex2))
Alternatives in branch reset group share same capturing group.

Regex Pattern - (?|(Haa)|(Hee)|(bye)|(k))\1

Test String - `HaaHaa` | `kk`

Given below is a Perl code.

```perl
$Regex_Pattern = '^(\d\d)(?|(---)|(-)|(\.)|(:))(\d\d)\2(\d\d)\2(\d\d)$';

$Test_String = <STDIN> ;
if($Test_String =~ /$Regex_Pattern/){
    print "true";
} else {
    print "false";
}
```

### 4. [Forward References](https://www.hackerrank.com/challenges/forward-references/problem)

**NOTE** - Forward reference is supported by JGsoft, .NET, Java, Perl, PCRE, PHP, Delphi and Ruby regex flavors.

Forward reference creates a back reference to a regex that would appear later.
Forward references are only useful if they're inside a repeated group.
Then there may arise a case in which the regex engine evaluates the backreference after the group has been matched already.

Regex Pattern - (\2amigo|(go!))+

Test String - `go!go!amigo`

Given below is a Perl code.

```
$Regex_Pattern = '^(\2tic|(tac))+$';

$Test_String = <STDIN> ;
if($Test_String =~ /$Regex_Pattern/){
    print "true";
} else {
    print "false";
}
```

