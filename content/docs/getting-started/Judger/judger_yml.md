---
title: With ToC
weight: 1
---
# Judger YAML

judger.yml 是对本次判题任务的一种描述。该文件里描述了本次判题需要执行的命令、判题数据位置、判题资源限制等。

我们会在运行每个判题容器前，向容器内放入该文件，该文件规定了这次容器要运行的命令，如何输出结果，运行的命令参数等。

## 字段名


一个典型的 `judger.yml` 如下：
	(img)
文件里规定了这些：
1. build 字段  
	  在 build 阶段需要执行的命令。
2. run 字段  
	  使用 [runner] 运行 build 的结果。
3. testdata 字段  
	  一个数组，每个元素是一组判题数据，格式为 `判题输入文件::判题输出文件`。
4. runner_args 字段  
	  [runner] 需要的 args，比如各种 limit，需要和 [runner] 的 args 一一对应并且字段相等。
