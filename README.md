# REGular EXpressions from [HackerRank](https://www.hackerrank.com/domains/regex) (with Solutions in Python 3)

## [Introduction](https://www.hackerrank.com/domains/regex?filters%5Bsubdomains%5D%5B%5D=re-introduction)
### 1. [Matching Specific String](https://www.hackerrank.com/challenges/matching-specific-string/problem)
Regex Pattern - wikipedia

Test String - https://en. `wikipedia` .org/
```
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
