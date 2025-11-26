# Assignment 2: Linux & Shell Scripting Tasks
**Name:** Sidhaant Singh Jyrwa  
**SAP ID:** 590029111
**Date:** 2025-11-23

## Aim
To perform scripting and system tasks covering file renaming, searching, Fibonacci generation, permission checks, system info, monitoring, text statistics, sorting, GCD/LCM, palindrome checks, and string operations.

## Requirements
- Linux system with bash
- Terminal access
- Text editor (nano/vim)

---

## Task 1: Add Prefix or Suffix to All Files in a Directory
**Script**
```bash
#!/bin/bash
read -p "Enter prefix or suffix (prefix: p:TEXT or suffix: s:TEXT): " opt
for f in *; do
  if [[ -f "$f" ]]; then
    if [[ "$opt" == p:* ]]; then
      p=${opt#p:}
      mv "$f" "${p}${f}"
    elif [[ "$opt" == s:* ]]; then
      s=${opt#s:}
      mv "$f" "${f}${s}"
    fi
  fi
done
```
**Output**
![dd6121d3492d5a6ffa9a96d87e7b1353.png](../_resources/dd6121d3492d5a6ffa9a96d87e7b1353.png)

---

## Task 2: Recursive File Search (by extension or size)
**Commands**
```bash
# Find by extension (e.g., .log)
find ~ -type f -name "*.log"

# Find files larger than 1MB
find ~ -type f -size +1M
```
**Output**
![44be35bcebc0dde9af90a85a1e5a2cf9.png](../_resources/44be35bcebc0dde9af90a85a1e5a2cf9.png)

---

## Task 3: Fibonacci Series up to N terms
**Script**
```bash
#!/bin/bash
read -p "Enter limit: " n
a=0; b=1
for ((i=0;i<n;i++)); do
  echo -n "$a "
  fn=$((a+b))
  a=$b
  b=$fn
done
echo
```
**Example Output**
```
Enter limit: 8
0 1 1 2 3 5 8 13
```

### Output:

![262874b060b6a843a9dd6765abc2a6de.png](../_resources/262874b060b6a843a9dd6765abc2a6de.png)

---

## Task 4: Check File Readable/Writable/Executable
**Commands**
```bash
read -p "Enter filename: " f
[ -r "$f" ] && echo "Readable" || echo "Not readable"
[ -w "$f" ] && echo "Writable" || echo "Not writable"
[ -x "$f" ] && echo "Executable" || echo "Not executable"
```
**Output**
![e59498728eb85ac74e3727d6de65ee54.png](../_resources/e59498728eb85ac74e3727d6de65ee54.png)

---

## Task 5: Display System Information
**Commands**
```bash
date
uptime
who
free -h
df -h
```
**Output**
![c96f8537c36a6b76032e2060f6ec4902.png](../_resources/c96f8537c36a6b76032e2060f6ec4902.png)

---

## Task 6: Continuously Monitor and Log Top Memory-Consuming Processes
**Script (one-shot)**
```bash
top -b -o %MEM -n 1 | head -20
```
**Script (continuous logging every minute)**
```bash
#!/bin/bash
while true; do
  echo "--- $(date) ---" >> memlog.txt
  top -b -o %MEM -n 1 | head -20 >> memlog.txt
  sleep 60
done
```
**Output**
![b40ebe1aa941aa0c4101da3fe2639223.png](../_resources/b40ebe1aa941aa0c4101da3fe2639223.png)

---

## Task 7: Count Lines, Words, Characters of a File
**Commands**
```bash
read -p "Enter filename: " f
wc "$f"
```
**Output**
![b3b38eb0b71fbefc577f406d0850e4b9.png](../_resources/b3b38eb0b71fbefc577f406d0850e4b9.png)

---

## Task 8: Accept Multiple Numbers and Sort Ascending
**Commands**
```bash
read -p "Enter numbers separated by spaces: " nums
echo $nums | tr ' ' '
' | sort -n | tr '\n' ' '
echo
```
**Output**
![96c90168889a1c1ec0d4a01e95d66fc1.png](../_resources/96c90168889a1c1ec0d4a01e95d66fc1.png)

---

## Task 9: Calculate GCD and LCM of Two Numbers
**Script**
```bash
#!/bin/bash
read -p "Enter two numbers: " a b
gcd() {
  local x=$1 y=$2 r
  while [ $y -ne 0 ]; do
    r=$(( x % y ))
    x=$y
    y=$r
  done
  echo $x
}
g=$(gcd $a $b)
l=$(( (a / g) * b ))
echo "GCD = $g"
echo "LCM = $l"
```
**Output**
![c93cf22851a8d5cde2d5d2dd8ca5a096.png](../_resources/c93cf22851a8d5cde2d5d2dd8ca5a096.png)

---

## Task 10: Check Palindrome String
**Commands**
```bash
read -p "Enter string: " s
rev=$(echo "$s" | rev)
if [[ "$s" == "$rev" ]]; then
  echo "Palindrome"
else
  echo "Not palindrome"
fi
```
**Output**
![e7d7430085f8cb2d85759ab015b391fe.png](../_resources/e7d7430085f8cb2d85759ab015b391fe.png)

---

## Task 11: Length of a String
**Commands**
```bash
read -p "Enter string: " s
echo "Length: ${#s}"
```
**Output**
![269b652586c97db501548af4040db132.png](../_resources/269b652586c97db501548af4040db132.png)

---

## Task 12: Reverse a Given String
**Commands**
```bash
read -p "Enter string: " s
echo "Reverse: $(echo "$s" | rev)"
```
**Output**
![c02a832eeffeb18f5e73372b1bb06c43.png](../_resources/c02a832eeffeb18f5e73372b1bb06c43.png)

---

## Task 13: Concatenate Two Input Strings
**Commands**
```bash
read -p "Enter first string: " s1
read -p "Enter second string: " s2
echo "Concatenated: ${s1}${s2}"
```
**Output**
![86d9d4b187daca7676739511826855a5.png](../_resources/86d9d4b187daca7676739511826855a5.png)

---

## Result
All tasks cover common scripting patterns, file operations, monitoring, and string/number processing useful for system administration and scripting practice.

## Conclusion
Assignment 2 provides practical tasks to strengthen shell scripting and Linux command-line proficiency.