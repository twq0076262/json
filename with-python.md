# 在 Python 中使用 JSON

本教程将会教我们如何使用 Python 编程语言编码和解码 JSON。让我们先来准备环境以便针对 JSON 进行 Python 编程。

## 环境

在我们使用 Python 编码和解码 JSON 之前，我们需要安装一个可用 JSON 模块。对于本教程请按照如下方式下载和安装 [Demjson](http://deron.meranda.us/python/demjson/)：

```
$tar xvfz demjson-1.6.tar.gz
$cd demjson-1.6
$python setup.py install
```

## JSON 函数

<table>
	<thead>
		<tr>
			<th>函数</th>
			<th>程序库</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>encode</td>
			<td>将 Python 对象编码为 JSON 字符串表示。</td>
		</tr>
		<tr>
			<td>decode</td>
			<td>将 JSON 编码的字符串解码为 Python 对象。</td>
		</tr>
	</tbody>
</table>

## 使用 Python 编码 JSON（encode）

Python 的 encode() 函数用于将 Python 对象编码为 JSON 字符串表示。

__语法：__

```
demjson.encode(self, obj, nest_level=0)
```

__示例：__

下面的例子展示了使用 Python 将数组转换为 JSON：

```
#!/usr/bin/python
import demjson

data = [ { 'a' : 1, 'b' : 2, 'c' : 3, 'd' : 4, 'e' : 5 } ]

json = demjson.encode(data)
print json
```

执行时会生成如下所示结果：

```
[{"a":1,"b":2,"c":3,"d":4,"e":5}]
```

## 使用 Python 解码 JSON（decode）

Python 可以使用 demjson.decode() 函数处理 JSON 解码。这个函数返回从 JSON 解码到适当 Python 类型的值。

__语法：__

```
demjson.decode(self, txt)
```

__示例：__

下面的例子展示了如何使用 Python 解码 JSON 对象。

```
#!/usr/bin/python
import demjson

json = '{"a":1,"b":2,"c":3,"d":4,"e":5}';

text = demjson.decode(json)
print text
```

执行时生成如下所示结果：

```
{u'a': 1, u'c': 3, u'b': 2, u'e': 5, u'd': 4}
```