## Experiment 6: Shell Loops

### Name: Sidhaant Singh Jyrwa Roll no.: 590029111 Date: 2025-09-05

### Aim:

* To understand and implement shell loops (`for`, `while`, `until`) in Bash.
* To practice loop control constructs (`break`, `continue`) and loop-based file processing.

### Requirements

* A Linux system with bash shell.
* A text editor (nano, vim) and permission to create and execute shell scripts.

## Theory

Loops allow repeated execution of commands until a condition is met. Common loop constructs in Bash include `for` (iterate over items), `while` (repeat while condition true), and `until` (repeat until condition becomes true). Loop control statements like `break` and `continue` change the flow inside loops. Loops are essential for automating repetitive tasks such as processing multiple files, generating sequences, and collecting user input.

## Procedure & Observations

## [Exercise 1: Simple `for` loop](/EXP6/for_simple.sh)

### Task Statement:

Write a `for` loop that prints numbers 1 to 5.

### Command(s):

```bash
for i in 1 2 3 4 5; do
  echo "Number: $i"
done
```

### Output:

![exp6_for_simple.png](/.img/exp6_for_simple.png)

---

## [Exercise 2: `for` loop over files](/EXP6/for_files.sh)

### Task Statement:

Process all `.txt` files in a directory and count lines in each.

### Command(s):

```bash
for f in *.txt; do
  echo "File: $f - Lines: $(wc -l < "$f")"
done
```

### Output:

![exp6_for_files.png](/.img/exp6_for_files.png)

---

## [Exercise 3: C-style `for` loop](/EXP6/for_cstyle.sh)

### Task Statement:

Use arithmetic C-style loop for numeric iteration.

### Command(s):

```bash
for ((i=0;i<5;i++)); do
  echo "i=$i"
done
```

### Output:

![exp6_for_cstyle.png](/.img/exp6_for_cstyle.png)

---

## [Exercise 4: `while` loop and reading input](/EXP6/while.sh)

### Task Statement:

Write a `while` loop that reads lines from a file or from user input.

### Command(s):

```bash
while read -r line; do
  echo "Line: $line"
done < sample.txt

while true; do
  read -p "Enter a number (0 to exit): " n
  if [[ $n -eq 0 ]]; then
    echo "Exiting..."; break
  fi
  echo "You entered: $n"
done
```

### Output:

![exp6_while](/.img/exp6_while.png)

---

## [Exercise 5: `until` loop](/EXP6/until.sh)

### Task Statement:

Use an `until` loop to run until a condition becomes true.

### Command(s):

```bash
count=1
until [ $count -gt 5 ]; do
  echo "count=$count"
  ((count++))
done
```

### Output:

![exp6_until](/.img/exp6_until.png)

---

## [Exercise 6: `break` and `continue`](/EXP6/break_continue.sh)

### Task Statement:

Demonstrate `break` and `continue` inside a loop.

### Command(s):

```bash
for i in {1..10}; do
  if [[ $i -eq 5 ]]; then
    echo "Reached 5, breaking"; break
  fi
  if (( i % 2 == 0 )); then
    echo "Skipping even $i"; continue
  fi
  echo "Processing $i"
done
```

### Output:

![exp6_break_continue](/.img/exp6_break_continue.png)

---

## [Exercise 7: Nested loops](/EXP6/nested.sh)

### Task Statement:

Create nested loops to generate a multiplication table.

### Command(s):

```bash
for i in {1..3}; do
  for j in {1..3}; do
    echo -n "$((i*j)) "
  done
  echo
done
```

### Output:

![exp6_nested](/.img/exp6_nested.png)

---

## Assignments

### [Assignment 1: Factorial of a Number](/EXP6/a1.sh)

### Command(s):

```bash
#!/bin/bash
echo -n "Enter a number: "
read num
fact=1
for ((i=1;i<=num;i++)); do
  fact=$((fact*i))
done
echo "Factorial of $num is $fact"
```

### Output:

![exp6_a1.png](/.img/exp6_a1.png)

---

### [Assignment 2: Fibonacci Series](/EXP6/a2.sh)

### Command(s):

```bash
#!/bin/bash
echo -n "Enter number of terms: "
read n
a=0
b=1
echo "Fibonacci series:"
for ((i=0;i<n;i++)); do
  echo -n "$a "
  fn=$((a+b))
  a=$b
  b=$fn
done
echo
```

### Output:

![exp6_a2.png](/.img/exp6_a2.png)

---

### [Assignment 3: Sum of Digits](/EXP6/a3.sh)

### Command(s):

```bash
#!/bin/bash
echo -n "Enter a number: "
read num
sum=0
temp=$num
while [ $temp -gt 0 ]; do
  digit=$((temp % 10))
  sum=$((sum + digit))
  temp=$((temp / 10))
done
echo "Sum of digits of $num is $sum"
```

### Output:

![exp6_a3.png](/.img/exp6_a3.png)

---

### [Assignment 4: Reverse a Number](/EXP6/a4.sh)

### Command(s):

```bash
#!/bin/bash
echo -n "Enter a number: "
read num
rev=0
temp=$num
while [ $temp -gt 0 ]; do
  digit=$((temp % 10))
  rev=$((rev * 10 + digit))
  temp=$((temp / 10))
done
echo "Reverse of $num is $rev"
```

### Output:

![exp6_a4.png](/.img/exp6_a4.png)

---

### [Assignment 5: Prime Number Check](/EXP6/a5.sh)

### Command(s):

```bash
#!/bin/bash
echo -n "Enter a number: "
read num
is_prime=1
for ((i=2;i<=num/2;i++)); do
  if (( num % i == 0 )); then
    is_prime=0
    break
  fi
done
if (( num <= 1 )); then
  echo "$num is not a prime number"
elif (( is_prime == 1 )); then
  echo "$num is a prime number"
else
  echo "$num is not a prime number"
fi
```

### Output:

![exp6_a5.png](/.img/exp6_a5.png)

---

## Result

* Implemented `for`, `while`, and `until` loops and used loop control statements.
* Practiced reading input, processing files, nested iteration, and completed assignments like factorial, Fibonacci, sum of digits, reverse number, and prime check.

## Challenges Faced & Learning Outcomes

* Challenge 1: Handling user input validation.
* Challenge 2: Managing arithmetic operations in loops.

### Learning:

* Loops are powerful for automation in shell scripting.
* Implementing small programs like factorial and Fibonacci builds confidence in shell scripting.

## Conclusion

The lab demonstrated practical loop constructs in Bash for automating repetitive tasks, and the assignments extended learning by applying loops to solve mathematical problems.