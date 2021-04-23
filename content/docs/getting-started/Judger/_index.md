---
weight: 10
---

# Judger

Judger 是我们的判题容器入口，帮忙在容器内编译用户代码，执行用户程序，举个例子：

它会根据 `judger.yml` 配置文件的内容来执行相应动作的工具。

## 工作流程

解析 judger.yml：
1. 根据 `language` 下载 preset
2. 根据 `env` 配置设置环境变量
3. 执行 `build` 阶段（编译用户代码）
4. 执行 `run` 阶段，运行所有测试用例

根据 run 结果执行操作：
1. 输出所有测试用例的结果
2. 将结果回调到规定的 callback 接口上

## 结果

```json
[
    {
        "status": "done",
        "message": "",
        "result": {
            "status": 0,
            "cpu_time_used": 1,
            "cpu_time_used_us": 1223,
            "real_time_used": 5,
            "real_time_used_us": 5201,
            "memory_used": 1488,
            "signal": 0,
            "exit_code": 0
        }
    },
    {
        "status": "done",
        "message": "",
        "result": {
            "status": 0,
            "cpu_time_used": 1,
            "cpu_time_used_us": 968,
            "real_time_used": 1,
            "real_time_used_us": 1210,
            "memory_used": 1588,
            "signal": 0,
            "exit_code": 0
        }
    }
]
```

可以看到，Judger 的输出是一个数组，图中的例子就是输出判断 c 语言的两个测试用例的结果。

每一项的 stdout 就是 runner 运行的判题结果。status 0 就是题目 AC 的意思。
