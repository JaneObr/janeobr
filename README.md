# №1
```
grep -oE '^[^:]+' /etc/passwd | sort
```

№2
cat /etc/protocols | awk '{print $2, $1}' | sort -nr | head -5

№3
#!/bin/bash

msg="$1"
border="+$(printf '%0.s-' $(seq ${#msg} + 2))+"

echo "$border"
echo "| $msg |"
echo "$border"

№4
grep -o '\b[a-zA-Z_][a-zA-Z0-9_]*\b' hello.py | sort | uniq

№5
#!/bin/bash

chmod +x "$1"
sudo cp "$1" /usr/local/bin/

№6
#!/bin/bash

# Обрабатываем каждый переданный файл
for file in "$@"; do
  # Проверяем, что файл имеет одно из указанных расширений
  if [[ "$file" =~ \.(c|js|py)$ ]]; then
    # Считываем первую строку файла
    first_line=$(head -n 1 "$file")
    # Проверяем, начинается ли первая строка с символов комментариев
    if [[ "$first_line" =~ ^# ]] || [[ "$first_line" =~ ^// ]]; then
      echo "File $file has a comment in the first line."
    else
      echo "File $file does not have a comment in the first line."
    fi
  fi
done

№7
find "$1" -type f -exec md5sum {} + | sort | uniq -w32 -dD

№8
find . -name "*.$1" -print0 | tar -cvzf archive.tar.qz --null -T -

№9
sed 's/    /\t/g' "$1" > "$2"

№10
find "$1"-type f -empty -name "*.txt"
