# JSON 数据类型

JSON 格式支持以下数据类型：

<table>
	<thead>
		<tr>
			<th>类型</th>
			<th>描述</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>数字型（Number）</td>
			<td>JavaScript 中的双精度浮点型格式</td>
		</tr>
		<tr>
			<td>字符串型（String）</td>
			<td>双引号包裹的 Unicode 字符和反斜杠转义字符</td>
		</tr>
		<tr>
			<td>布尔型（Boolean）</td>
			<td>true 或 false</td>
		</tr>
		<tr>
			<td>数组（Array）</td>
			<td>有序的值序列</td>
		</tr>
		<tr>
			<td>值（Value）</td>
			<td>可以是字符串，数字，true 或 false，null 等等</td>
		</tr>
		<tr>
			<td>对象（Object）</td>
			<td>无序的键:值对集合</td>
		</tr>
		<tr>
			<td>空格（Whitespace）</td>
			<td>可用于任意符号对之间</td>
		</tr>
		<tr>
			<td>null</td>
			<td>空</td>
		</tr>
	</tbody>
</table>

## 数字型

- JavaScript 中的双精度浮点型格式，取决于实现。
- 不能使用八进制和十六进制格式。
- 在数字中不能使用 NaN 和 Infinity。

下表展示了数字类型：

<table>
	<thead>
		<tr>
			<th>类型</th>
			<th>描述</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>整形（Integer）</td>
			<td>数字1-9，0和正负数</td>
		</tr>
		<tr>
			<td>分数（Fraction）</td>
			<td>分数，比如 .3，.9</td>
		</tr>
		<tr>
			<td>指数（Exponent）</td>
			<td>指数，比如 e，e+，e-，E，E+，E-</td>
		</tr>
	</tbody>
</table>

__语法：__

```
var json-object-name = { string : number_value, .......}
```

__示例：__

下面的示例展示了数字类型，其值不应该使用引号包裹：

```
var obj = {marks: 97}
```

## 字符串型

- 零个或多个双引号包裹的 Unicode 字符以及反斜杠转义序列。
- 字符就是只有一个字符的字符串，长度为 1。

下表展示了字符串类型：

<table>
	<thead>
		<tr><th>类型</th><th>描述</th></tr>
	</thead>
	<tbody>
		<tr><td>"</td><td>双引号</td></tr>
		<tr><td>\</td><td>反斜线</td></tr>
		<tr><td>/</td><td>斜线</td></tr>
		<tr><td>b</td><td>退格符</td></tr>
		<tr><td>f</td><td>换页符</td></tr>
		<tr><td>n</td><td>换行符</td></tr>
		<tr><td>r</td><td>回车符</td></tr>
		<tr><td>t</td><td>水平制表符</td></tr>
		<tr><td>u</td><td>四位十六进制数字</td></tr>
	</tbody>
</table>

__语法：__

```
var json-object-name = { string : "string value", .......}
```

__示例：__

下面的示例展示了字符串数据类型：

```
var obj = {name: 'Amit'}
```

## 布尔型

它包含 true 和 false 两个值。

__语法：__

```
var json-object-name = { string : true/false, .......}
```

__示例：__

```
var obj = {name: 'Amit', marks: 97, distinction: true}
```

## 数组

- 它是一个有序的值集合。
- 使用方括号闭合，这意味着数组以 [ 开始，以 ] 结尾。
- 值使用 ,（逗号）分割。
- 数组索引可以以 0 或 1 开始。
- 当键名是连续的整数时应该使用数组。

__语法：__

```
[ value, .......]
```

__示例：__

下面的示例展示了一个包含多个对象的数组：

```
{
	"books": [
		{ "language":"Java" , "edition":"second" },
		{ "language":"C++" , "lastName":"fifth" },
		{ "language":"C" , "lastName":"third" }
	]
}
```

## 对象

- 它是一个无序的名/值对集合。
- 对象使用大括号闭合，以 '{' 开始，以 '}' 结尾。
- 每个名称后面都跟随一个 ':'（冒号），名/值对使用 ,（逗号）分割。
- 键名必须是字符串，并且不能同名。
- 当键名是任意字符串时应该使用对象。

__语法：__

```
{ string : value, .......}
```

__示例：__

下面的例子展示了对象：

```
{
	"id": "011A",
	"language": "JAVA",
	"price": 500,
}
```

## 空格

可以在任意一对符号之间插入。可以添加用来让代码更可读。下面的例子展示了使用空格和不使用空格的声明：

__语法：__

```
{string:"   ",....}
```

__示例：__

```
var i= "   sachin";
var j = "  saurav"
```

## null

意味着空类型。

__语法：__

```
null
```

__示例：__

```
var i = null;

if(i==1) {
	document.write("<h1>value is 1</h1>");	
} else {
	document.write("<h1>value is null</h1>");
}
```

## JSON 值

包括：

- 数字（整型和浮点型）
- 字符串
- 布尔值
- 数组
- 对象
- null

__语法：__

```
String | Number | Object | Array | TRUE | FALSE | NULL
```

__示例：__

```
var i =1;
var j = "sachin";
var k = null;
```