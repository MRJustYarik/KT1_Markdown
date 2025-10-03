```go
package main

import "fmt"

//Пользовательский тип, на основе ссреза
type elems []int

func main(){
	

	// Используем наш тип вместо обычного среза
    var nums elems = []int{1, 2, 3}
    
    nums = append(nums, 4)
    fmt.Println(nums) // [1 2 3 4]
    
    add(&nums, 5)
    fmt.Println(nums) // [1 2 3 4 5]

    // Теперь можно использовать метод!
    nums.add(6)
    fmt.Println(nums) // [1 2 3 4 5 6]
    
    nums.add(7).add(8) // Если сделать метод с возвратом значения
    fmt.Println(nums)
    
    fmt.Println("Длина:", nums.length()) // Длина: 8
}

func add(arr *elems, num int){
	*arr = append(*arr, num);
}

func (e *elems) add(num int) *elems{
	*e = append(*e, num);
	return e 
}

func (e *elems) set(index, num int){
	if index >= 0 && index < len(*e) {
		(*e)[index] = num
	}
}

func (e *elems) length() int{
	return len(*e)
}
```