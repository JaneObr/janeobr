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
![IMAGE 2024-09-16 23:28:37](https://github.com/user-attachments/assets/cd7b02cd-2fe9-4025-a856-03f40be70d19)

# №5
```
#!/bin/bash
 
if [ "$#" -ne 1 ]; then
        echo "Использование: $0 <имя_файла>"
        exit 1
fi
 
COMMAND=$1
 
 
if [ ! -f "$COMMAND" ]; then
        echo "Ошибка: файл $COMMAND не существует."
        exit 1
fi
 
sudo cp "$COMMAND" /usr/local/bin/
 
if [ $? -ne 0 ]; then
        echo "Ошибка: не удалось скопировать файл в /usr/local/bin."
        exit 1
fi
 
sudo chmod 755 /usr/local/bin/"$COMMAND"
 
if [ $? -ne 0 ]; then
        echo "Ошибка: не удалось установить права доступа."
        exit 1
fi
 
echo "Команда $COMMAND успешно зарегистрирована в /usr/local/bin."
```
![IMAGE 2024-09-16 23:28:39](https://github.com/user-attachments/assets/6dfe606f-7b07-4179-a2e4-6adcc2943158)

# №6
```
check_comment() {
        local file=$1 local first_line=$(head -n 1 "$file")
        if [[ "$first_line" =~ ^[[:space:]]*# ]]; then
                echo "Файл $file: Комментарий найден"
        else
                echo "Файл $file: Комментарий не найден"
        fi
}
for ext in c js py; do
        for file in *."$ext"; do
                if [ -f "$file" ]; then
                        check_comment "$file"
                fi
        done
done
```
![IMAGE 2024-09-16 23:28:42](https://github.com/user-attachments/assets/c14926dd-5482-4020-b947-ec175cdabfe0)

# №7
```
find "$1" -type f -exec md5sum {} + | sort | uniq -w32 -dD
```
![IMAGE 2024-09-16 23:28:44](https://github.com/user-attachments/assets/21ecd787-89c6-4ab2-a27b-bda704b6194a)

# №8
```
tar -czvf archive.tar.gz $(find . -type f -name "*.txt")
```
![IMAGE 2024-09-16 23:28:47](https://github.com/user-attachments/assets/dc62413d-ddd1-44ba-b8dd-ed56b7bcb4cb)

# №9
```
s#!/bin/bash

if [ "$#" -ne 2 ]; then
    echo "Usage: $0 input_file output_file"
    exit 1
fi

input_file="$1"
output_file="$2"

if [ ! -f "$input_file" ]; then
    echo "Error: Input file '$input_file' does not exist."
    exit 1
fi

sed 's/    /\t/g' "$input_file" > "$output_file"
```
![IMAGE 2024-09-17 10:00:00](https://github.com/user-attachments/assets/2409272f-49e2-4d10-bd92-e92b4c15cfcb)


# №10
```
find "/home/user/documents" -type f -name "*.txt" -exec bash -c '[[ $(wc -c < "$1") -eq 0 ]] && echo "$1" ' _ {} \;
```
![IMAGE 2024-09-16 23:28:51](https://github.com/user-attachments/assets/a72a4bbb-ceef-476f-beae-97fbb5a91032)
