# REGular EXpressions from [HackerRank](https://www.hackerrank.com/domains/regex) (with Solutions in Python 3)

## 1. [Matching Specific String](https://www.hackerrank.com/challenges/matching-specific-string/problem)

```
Regex_Pattern = r'hackerrank'	# Do not delete 'r'.

import re
Test_String = input()
match = re.findall(Regex_Pattern, Test_String)
print("Number of matches :", len(match))
```
