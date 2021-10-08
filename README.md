# 1. forked from [go-playground/validator](https://github.com/go-playground/validator)
# 2. 源码中required_if只能对同级元素或者子级元素进行校验 添加required_if_global校验方法可校验任何层级
# 3. 使用方法
```go
package main

type Address struct {
	SendAddress struct{
		Province string
	}
	ReceiveAddress struct{
		Province string `validate:"required_if_global=SendAddress.Province shanghai"`
	}
}
```