# 在 Ruby 中使用 JSON

本教程将会教我们如何使用 Ruby 编程语言编码和解码 JSON。下面我们先为 JSON 准备好 Ruby 编程环境。

## 环境

在我们使用 Ruby 编码和解码 JSON 之前，我们需要安装一个可用于 Ruby 的 JSON 模块。你可能需要安装 Ruby gem，如果你使用的是最新版的 Ruby，那么你必须在你的机器上安装 gem，安装好 gem 之后遵循下面这个步骤：

```
$gem install json
```

## 使用 Ruby 解析 JSON

下面的例子展示了前 2 个键持有字符串值，最后 3 个键持有字符串数组。我们把下面的内容保存为叫做 __input.json__ 的文件。

```
{
	"President": "Alan Isaac",
	"CEO": "David Richardson",
	"India": [
		"Sachin Tendulkar",
		"Virender Sehwag",
		"Gautam Gambhir"
	],
	"Srilanka": [
		"Lasith Malinga",
		"Angelo Mathews",
		"Kumar Sangakkara"
	],
	"England": [
		"Alastair Cook",
		"Jonathan Trott",
		"Kevin Pietersen"
	]
}
```

下面是用于解析上述 JSON 文档的 Ruby 程序：

```
#!/usr/bin/ruby
require 'rubygems'
require 'json'
require 'pp'

json = File.read('input.json')
obj = JSON.parse(json)

pp obj
```

执行时生成如下所示结果：

```
{
	"President"=>"Alan Isaac",
	"CEO"=>"David Richardson",

	"India"=>
		["Sachin Tendulkar", "Virender Sehwag", "Gautam Gambhir"],

	"Srilanka"=>
		["Lasith Malinga ", "Angelo Mathews", "Kumar Sangakkara"],

	"England"=>
		["Alastair Cook", "Jonathan Trott", "Kevin Pietersen"]
}
```