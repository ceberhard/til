## How to get the number of instances of a sub-string in a larger string
When you have a particular string variable (TXT_TO_SEARCH) and you need to find the number of times another string (TXT_TO_FIND) appears in that larger variable, you can use the ```grep``` command like so:
```bash
grep -o "$TXT_TO_FIND" <<< "$TXT_TO_SEARCH" | wc -l
```

### Sample
https://github.com/ceberhard/rosalind/blob/master/problem_DNA/solution.sh
