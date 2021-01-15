```
package main

import "fmt"

// 从后面判断（比较好 推荐）
// dd := "a/b/c.go" 从后面判断符号是否为 "/" 从而进行字符串切割

 // s=[ i-1:] 就可以实现basename命令了
func basenameqin(s string) {
	for i := len(s) - 1; i >= 0; i-- {
		if s[i] == '/' {
			s = s[:i]
   // s=[ i-1:]
			break
		}
	}
	fmt.Println(s)
}

//  从前面判断
// dd := "a/b/c.go" 从前面判断符号是否为 "/" 从而进行字符串切割
// 弊端 比较多次属判断以及增加多个变量
func dirnameqin(s string) {
	var str string
	for i := 0; i <= len(s)-1; i++ {
		if s[i] == '/' {
			str = s[:i]
		}
	}
	fmt.Println(str)
}

func main() {
	dd := "a/b/c.go"
	dirnameqin(dd)
	basenameqin(dd)

}

PS D:\Golang\src\qin> go run qq.go
a/b
a/b
```

