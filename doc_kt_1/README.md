# Инструменты для разработки технической документации
## ФИО: Оконечников Ярослав Васильевич

Сайт колледжа [lxp](https://newlxp.ru/).

### Шпаргалка по Git
📥 Клонировать репозиторий
- git clone [ссылка-на-репозиторий]
- cd [папка-проекта]

🌿 Создать новую ветку
- git checkout -b [название-ветки]

➕ Добавить файлы в коммит
- git add .
- git commit -m "Описание изменений"

🔄 Переключиться между ветками
- git checkout [название-ветки]

↩️ Отменить изменения
- git checkout -- [имя-файла]

💾 Сохранить и залить изменения
- git add .
- git commit -m "Описание изменений"
- git push origin [название-ветки]

📥 Загрузить обновления
- git pull

Отменить последний коммит
- git reset [файл] (Отменить добавление файлов)
- git reset --soft HEAD~1 (сохранить изменения)
- git reset --hard HEAD~1 (удалить изменения)

**Пример блока кода**
```go
package main

import "fmt"

func main(){
	numbers := []int{1, 2, 3}
	numbers = append(numbers, 4)
	fmt.Println(numbers)
	add(&numbers, 5)
	fmt.Println(numbers)
}


func add(arr *[]int, num int){
	*arr = append(*arr, num);
}

```