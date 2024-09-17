# №1
Вывести отсортированный в алфавитном порядке список имен пользователей в файле passwd (вам понадобится grep).
```
grep -oE '^[^:]+' /etc/passwd | sort
```
https://private-user-images.githubusercontent.com/162557348/367662775-010029c3-9fd1-42aa-9a78-aa5aef786b7f.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MjY1NTU1ODQsIm5iZiI6MTcyNjU1NTI4NCwicGF0aCI6Ii8xNjI1NTczNDgvMzY3NjYyNzc1LTAxMDAyOWMzLTlmZDEtNDJhYS05YTc4LWFhNWFlZjc4NmI3Zi5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwOTE3JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDkxN1QwNjQxMjRaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT02YTBmYTQwYTNlODdkMzY2Zjg5ZWJhMGFmMzBiNTI2ZDVkNTYwMWY4NDMxNGVhNzZkZTRlZThjNWYyNTU4ZmUwJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.W2usemH2kBxh_r9VYp1QsRr8btIxRBB6KDXLzvg-MZQ![image](https://github.com/user-attachments/assets/c30f8bfc-6628-4ada-b757-98deb18dca97)



# №2
```
cat /etc/protocols | awk '{print $2, $1}' | sort -nr | head -5
```
# №3
```
#!/bin/bash
text=$1
size=${#text}
echo -n "+"
for ((i = -2; i < size; i++))
do
echo -n "-"
done
echo "+"
echo "| $text |"
echo -n "+"
for ((i = -2; i < size; i++))
do
echo -n "-"
done
echo "+"
```
# №4
```
grep -oE '\b[a-zA-Z_][a-zA-Z0-9_]*\b' hello.go | grep -vE '\b(int|void|return|if|else|for|while|include|stdio)\b' | sort | uniq
```
# №5
```
#!/bin/bash
file=$1
chmod 755 "./$file"
sudo cp "$file" /usr/local/bin/
```
# №6
```

```
# №7
```
find "$1" -type f -exec md5sum {} + | sort | uniq -w32 -dD
```
# №8
```
find . -name "*.$1" -print0 | tar -cvzf archive.tar.qz --null -T -
```
# №9
```
sed 's/    /\t/g' "$1" > "$2"
```
# №10
```
find "$1"-type f -empty -name "*.txt"
```
