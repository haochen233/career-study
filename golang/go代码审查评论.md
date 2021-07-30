### context

- 大多数使用Context的函数都应将其作为第一个参数：
- 不要将Context成员添加到结构类型；而是将ctx参数添加到该类型需要传递的每个方法上。
- 上下文是不可变的，因此可以将相同的ctx传递给共享相同截止时间，取消信号，凭据，父级跟踪等的多个调用

### rand随机数生成

- 不要使用math/rand来生成，它的生成器是完全可以预测的
- 请使用crypto/rand的Read函数

### 声明空切片（declare empty slice）

- 优先选择 `var t []string`
- 次选 `t := []string{}`
- 第一选择是一个`nil` 切片，第二选择是一个`len`,`cap`都为0的非nil切片。第一种nil slice是首选的风格
- 请注意，在少数情况下，首选非`nil`但`len`为零的切片（第二选择）。因为的`json`编码时，`nil`切片会被编码为`null`对象，非`nil`但`len为`零的切片被编码为`Json`数组 `[]`

### 不要 panic

- 不需要对常规错误处理使用`panic`，使用错误和多个返回值。

### 错误字符串（Error Strings）

- 错误字符串不应大写，或以标点符号结尾。
- 请使用`fmt.Errorf("something bad")`不要使用`fmt.Errorf("Something bad")`

