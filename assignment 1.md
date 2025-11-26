# Assignment 1: Linux Commands & Shell Scripting Report
**Name:** Sidhaant Singh Jyrwa  
**SAP ID:** 590029111
**Date:** 2025-11-23 

## Aim
To perform and demonstrate Linux file handling, permissions, text processing, redirection, search, archiving, networking, and shell scripting operations through 10 structured tasks.

## Requirements
- Linux system (Ubuntu/Linux Mint/Debian)
- Terminal access
- Text editor (nano/vim)
- Internet connection (for ping)

## Task 1: File and Directory Commands
### Commands
```
mkdir ~/MyLinuxFiles
cd ~/MyLinuxFiles
touch file1.txt file2.txt file3.txt
ls -l
```
### Output
![338c4598220b6a902be89f1899c3755d.png](/.img/338c4598220b6a902be89f1899c3755d.png)

## Task 2: File Permissions
### Commands
```
chmod 640 file1.txt
ls -l file1.txt
```
### Output
![fd36c6c355c0aab69c37eaa9ee888f9c.png](/.img/fd36c6c355c0aab69c37eaa9ee888f9c.png)

## Task 3: Text Processing
### Commands
```
grep "Linux" notes.txt
grep -c "Linux" notes.txt
```
### Output
![7e90a725ee127e997a7fa6292fe7517a.png](/.img/7e90a725ee127e997a7fa6292fe7517a.png)

## Task 4: Redirection and Pipes
### Commands
```
sort file1.txt > sorted.txt
cat sorted.txt
```
### Output
![5e29aca9a63abbb443766b92b3042a50.png](/.img/5e29aca9a63abbb443766b92b3042a50.png)

## Task 5: Shell Scripting – Arithmetic
### Script
```
#!/bin/bash
read -p "Enter first number: " a
read -p "Enter second number: " b

echo "Sum: $((a+b))"
echo "Difference: $((a-b))"
echo "Product: $((a*b))"

if [ $b -eq 0 ]; then
  echo "Error: Division by zero is not allowed"
else
  echo "Quotient: $((a/b))"
fi
```
### Output
![b9d22894387ab5d98b924bde568e27e3.png](/.img/b9d22894387ab5d98b924bde568e27e3.png)

## Task 6: File Searching
### Commands
```
find ~ -name "*.txt" -mtime -7
```
### Output
![b74818ede3dfe230d41362f778e8acff.png](/.img/b74818ede3dfe230d41362f778e8acff.png)

## Task 7: Archiving and Compression
### Commands
```
tar -cvf MyLinuxFiles.tar MyLinuxFiles
gzip MyLinuxFiles.tar
tar -xvf MyLinuxFiles.tar.gz
```
### Output
![258ab5f045745149688bcd74799ad040.png](/.img/258ab5f045745149688bcd74799ad040.png)

## Task 8: Networking
### Commands
```
ip a
ping -c 4 google.com
```
### Output
![025617399b0593018b647d13c5c814ee.png](/.img/025617399b0593018b647d13c5c814ee.png)

## Task 9: Largest of Three Numbers
### Script
```
#!/bin/bash
read -p "Enter three numbers: " a b c

if (( a>=b && a>=c )); then
  echo "$a is the largest"
elif (( b>=a && b>=c )); then
  echo "$b is the largest"
else
  echo "$c is the largest"
fi
```
### Output
![b02f01f8fd64a1048e7b4d9d2f186e78.png](/.img/b02f01f8fd64a1048e7b4d9d2f186e78.png)

## Task 10: Sum of First N Natural Numbers
### Script
```
#!/bin/bash
read -p "Enter N: " n
sum=0

for ((i=1; i<=n; i++)); do
  sum=$((sum+i))
done

echo "Sum of first $n natural numbers = $sum"
```
### Output
![d415bdfcaf523744cf6b22c9ba8a5221.png](/.img/d415bdfcaf523744cf6b22c9ba8a5221.png)

## Result
All 10 tasks of Assignment-1 were successfully executed.

## Conclusion
This assignment strengthened fundamental Linux skills and provided hands-on practice.