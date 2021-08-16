原文：https://www.rfc-editor.org/rfc/rfc1035.html

## 三、域名空间和RR（Resource Record）定义

### 名称空间定义

```txt
labels          63 octets or less

names           255 octets or less

TTL             positive values of a signed 32 bit number.

UDP messages    512 octets or less
```
域名在消息中以label序列表示，每个label表示为一个8bit位长度的字段。因为每个域名都以根的空标签结束，所以域名以零长字节结束.8bit为中的高2位必须是0，剩下的6位限制这个label少于63个字节。

为了简化实现，域名的总长度(即标签字节和标签长度字节)被限制为255字节或更少。