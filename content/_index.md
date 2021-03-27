---
title: Introduction
type: docs
---

# Judgoo

一个更省心，更安全以及更快的运行代码的平台。

{{< columns >}}

## 运行代码

提交代码以及标准输入，系统可以返回代码的运行结果。

<--->

## 判题服务

程序设计的判题服务我们也支持！  

支持 SPJ！  
支持判题数据分步得分！  
支持内存、时间限制！

<--->

## 恐怖如斯

强大的特性数都数不过来

1. 分布式容器判题  
2. 支持代码规范评测


{{< /columns >}}

## 开始使用

### 运行代码

只需使用 HTTP Client 发送 POST 请求即可，暂时只支持单文件。

```http
POST /v1/judge/python/3.6 HTTP/1.1
Content-Type: application/json; charset=utf-8
Host: JudgeX:3000
Content-Length: 28

{"id":1,"code":"print(123)"}
```

嘿，您说多地道。
