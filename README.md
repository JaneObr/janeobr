# №1
Вывести отсортированный в алфавитном порядке список имен пользователей в файле passwd (вам понадобится grep).
```
grep -oE '^[^:]+' /etc/passwd | sort
```
[image](https://github.com/user-attachments/assets/c30f8bfc-6628-4ada-b757-98deb18dca97)



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
