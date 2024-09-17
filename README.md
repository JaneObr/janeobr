# №1
```
# grep -E '^[^:]+' /etc/passwd | sort
```
![IMAGE 2024-09-16 23:28:29](https://github.com/user-attachments/assets/5334ca29-f16c-4ee5-86b1-da95783666f5)

# №2
```
~#cat /etc/protocols | awk '{print $2, $1}' | sort -nr | head -5
```
![IMAGE 2024-09-16 23:28:31](https://github.com/user-attachments/assets/e7f91315-cefc-4c09-82e7-2969e7b0fff5)

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
<img width="564" alt="image" src="https://github.com/user-attachments/assets/e7bde14d-cfc4-408d-a231-62f8b3e1f06e">

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
