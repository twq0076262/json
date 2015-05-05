# JSON 快速指南

JSON 或者 JavaScript 对象表示法是一种轻量级的基于文本的开放标准，被设计用于可读的数据交换。约定使用 JSON 的程序员包括 C，C++，Java，Python，Perl 等等。

- JSON 代表 JavaScript 对象表示法。
- 这个格式由 Douglas Crockford 提出。
- 被设计用于可读的数据交换。
- 它已经被扩展到 JavaScript 脚本语言中。
- 文件名扩展是 __.json__。
- JSON 的网络媒体类型是 __application/json__。
- 统一标示符类型（Uniform Type Identifier）是 public.json。

## JSON 使用范围

- 用于编写基于 JavaScript 应用程序，包括浏览器扩展和网站。
- JSON 格式可以用于通过网络连接序列化和传输结构化数据。
- 主要用于在服务器和 Web 应用程序之间传输数据。
- Web 服务和 APIs 可以使用 JSON 格式提供公用数据。
- 还可以用于现代编程语言中。

## JSON 特点

- JSON 容易阅读和编写。
- 它是一种轻量级的基于文本的交换格式。
- 语言无关。

## JSON 简单示例

鉴于书籍数据有语言和版本信息，下面的例子展示了使用 JSON 存储书籍信息：

```
{
	"book": [
		{
			"id":"01",
			"language": "Java",
			"edition": "third",
			"author": "Herbert Schildt"
		},
		{
			"id":"07",
			"language": "C++",
			"edition": "second"
			"author": "E.Balagurusamy"
	}]
}
```

理解上述程序之后我们来看另外一个例子，让我们把下面的代码保存为 __json.htm__：

```
<html>
<head>
<title>JSON example</title>
<script language="javascript" >
  
	var object1 = { "language" : "Java", "author"  : "herbert schildt" };
	document.write("<h1>JSON with JavaScript example</h1>");
	document.write("<br>");
	document.write("<h3>Language = " + object1.language+"</h3>");  
	document.write("<h3>Author = " + object1.author+"</h3>");   

	var object2 = { "language" : "C++", "author"  : "E-Balagurusamy" };
	document.write("<br>");
	document.write("<h3>Language = " + object2.language+"</h3>");  
	document.write("<h3>Author = " + object2.author+"</h3>");   

	document.write("<hr />");
	document.write(object2.language + " programming language can be studied " +
	"from book written by " + object2.author);
	document.write("<hr />");
  
</script>
</head>
<body>
</body>
</html>
```

现在尝试使用 IE 或者其他任何启用了 JavaScript 的浏览器打开这个页面，它会生成如下所示结果：

![json example demo](images/json_example_demo.jpg)

## JSON 语法

我们来快速浏览器一下 JSON 的基本语法。JSON 的语法基本上可以视为 JavaScript 语法的一个子集，包括以下内容：

- 数据使用名/值对表示。
- 使用大括号保存对象，每个名称后面跟着一个 ':'（冒号），名/值对使用 , （逗号）分割。
- 使用方括号保存数组，数组值使用 ,（逗号）分割。

下面是一个简单的示例：

```
{
	"book": [
		{
			"id":"01",
			"language": "Java",
			"edition": "third",
			"author": "Herbert Schildt"
		},
		{
			"id":"07",
			"language": "C++",
			"edition": "second"
			"author": "E.Balagurusamy"
	}]
}
```

JSON 支持一下两种数据结构：

- __名/值对集合：__ 这一数据结构由不同的编程语言支持。
- __有序的值列表：__ 包括数组，列表，向量或序列等等。

## JSON 数据类型

JSON 格式支持以下数据类型

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

### 数字型

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

### 字符串型

- 零个或多个双引号包裹的 Unicode 字符以及反斜杠转义序列。
- 字符就是只有一个字符的字符串，长度为 1。

下表展示了字符串类型：

<table>
	<thead>
		<tr><th>类型</th><th>描述</th></tr>
	</thead>
	<tbody>
		<tr><td>"</td><td> 双引号 </td></tr>
		<tr><td>\</td><td> 反斜线 </td></tr>
		<tr><td>/</td><td> 斜线</td></tr>
		<tr><td>b</td><td> 推格符 </td></tr>
		<tr><td>f</td><td> 换页符 </td></tr>
		<tr><td>n</td><td> 换行符 </td></tr>
		<tr><td>r</td><td> 回车符 </td></tr>
		<tr><td>t</td><td> 水平制表符 </td></tr>
		<tr><td>u</td><td> 四位十六进制数字 </td></tr>
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

### 布尔型

它包含 true 和 false 两个值。

__语法：__

```
var json-object-name = { string : true/false, .......}
```

__示例：__

```
var obj = {name: 'Amit', marks: 97, distinction: true}
```

### 数组

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

### 对象

- 一个无序的名/值对集合。
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

### 空格

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

### null

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

### JSON 值

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

## JSON 对象

### 创建简单的对象

JSON 对象可以使用 JavaScript 创建。我们来看看使用 JavaScript 创建 JSON 对象的各种方式：

- 创建一个空对象：

```
var JSONObj = {};
```

- 创建一个新对象：

```
var JSONObj = new Object();
```

- 创建一个 __bookname__ 属性值为字符串，__price__属性值为数字的对象。可以通过使用 '.' 运算符访问属性。

```
var JSONObj = { "bookname ":"VB BLACK BOOK", "price":500 };
```

这里有一个例子，展示了在 JavaScript 中使用 JSON 创建对象，可以将下面的代码保存为 __json_object.htm__：

```
<html>
<head>
<title>Creating Object JSON with JavaScript</title>
<script language="javascript" >

	var JSONObj = { "name" : "tutorialspoint.com", "year"  : 2005 };
	document.write("<h1>JSON with JavaScript example</h1>");
	document.write("<br>");
	document.write("<h3>Website Name="+JSONObj.name+"</h3>");  
	document.write("<h3>Year="+JSONObj.year+"</h3>");  

</script>
</head>
<body>
</body>
</html>
```

尝试使用 IE 或者任何其他启用了 JavaScript 的浏览器打开这个页面，生成的结果如下所示：

![json object](images/json_objects.jpg)

### 创建数组对象

下面的例子展示了在 JavaScript 中使用 JSON 创建数组对象，可以将下面的代码保存为 __json_array_object.htm__：

```
<html>
<head>
<title>Creation of array object in javascript using JSON</title>
<script language="javascript" >

document.writeln("<h2>JSON array object</h2>");

var books = {
	"Pascal" : [ 
		{ "Name"  : "Pascal Made Simple", "price" : 700 },
		{ "Name"  : "Guide to Pascal", "price" : 400 }
	],                       
	"Scala"  : [
		{ "Name"  : "Scala for the Impatient", "price" : 1000 }, 
		{ "Name"  : "Scala in Depth", "price" : 1300 }
	]    
}    

var i = 0
document.writeln("<table border='2'><tr>");
for(i=0;i<books.Pascal.length;i++)
{	
	document.writeln("<td>");
	document.writeln("<table border='1' width=100 >");
	document.writeln("<tr><td><b>Name</b></td><td width=50>"
	+ books.Pascal[i].Name+"</td></tr>");
	document.writeln("<tr><td><b>Price</b></td><td width=50>"
	+ books.Pascal[i].price +"</td></tr>");
	document.writeln("</table>");
	document.writeln("</td>");
}

for(i=0;i<books.Scala.length;i++)
{
	document.writeln("<td>");
	document.writeln("<table border='1' width=100 >");
	document.writeln("<tr><td><b>Name</b></td><td width=50>"
	+ books.Scala[i].Name+"</td></tr>");
	document.writeln("<tr><td><b>Price</b></td><td width=50>"
	+ books.Scala[i].price+"</td></tr>");
	document.writeln("</table>");
	document.writeln("</td>");
}
document.writeln("</tr></table>");
</script>
</head>
<body>
</body>
</html>
```

接下来尝试使用 IE 或者任意其他启用了 JavaScript 的浏览器打开这个页面，生成的结果如下所示：

![json array object](images/json_array_objects.jpg)

## JSON 模式（Schema）

JSON 模式是一种基于 JSON 格式定义 JSON 数据结构的规范。它被写在 IETF 草案下并于 2011 年到期。JSON 模式：

- 描述现有数据格式。
- 干净的人类和机器可读的文档。
- 完整的结构验证，有利于自动化测试。
- 完整的结构验证，可用于验证客户端提交的数据。

### JSON 模式验证库

目前有好几个验证器可用于不同的编程语言。但是目前最完整和兼容 JSON 模式的验证器是 JSV。

<table>
	<tbody>
		<tr>
			<th>
				语言
			</th>
			<th>
				库
			</th>
		</tr>
		<tr>
			<td>
				C
			</td>
			<td>
				WJElement (LGPLv3)
			</td>
		</tr>
		<tr>
			<td>
				Java
			</td>
			<td>
				json-schema-validator (LGPLv3)
			</td>
		</tr>
		<tr>
			<td>
				.NET
			</td>
			<td>
				Json.NET (MIT)
			</td>
		</tr>
		<tr>
			<td>
				ActionScript 3
			</td>
			<td>
				Frigga (MIT)
			</td>
		</tr>
		<tr>
			<td>
				Haskell
			</td>
			<td>
				aeson-schema (MIT)
			</td>
		</tr>
		<tr>
			<td>
				Python
			</td>
			<td>
				Jsonschema
			</td>
		</tr>
		<tr>
			<td>
				Ruby
			</td>
			<td>
				autoparse (ASL 2.0); ruby-jsonschema (MIT)
			</td>
		</tr>
		<tr>
			<td>
				PHP
			</td>
			<td>
				php-json-schema (MIT). json-schema (Berkeley)
			</td>
		</tr>
		<tr>
			<td>
				JavaScript
			</td>
			<td>
				Orderly (BSD); JSV; json-schema; Matic (MIT); Dojo; Persevere (modified
				BSD or AFL 2.0); schema.js.
			</td>
		</tr>
	</tbody>
</table>

### JSON 模式示例

下面是一个基本的 JSON 模式，其中涵盖了一个经典的产品目录说明：

```
{
	"$schema": "http://json-schema.org/draft-04/schema#",
	"title": "Product",
	"description": "A product from Acme's catalog",
	"type": "object",
	"properties": {
		"id": {
			"description": "The unique identifier for a product",
			"type": "integer"
		},
		"name": {
			"description": "Name of the product",
			"type": "string"
		},
		"price": {
			"type": "number",
			"minimum": 0,
			"exclusiveMinimum": true
		}
	},
	"required": ["id", "name", "price"]
}
```

我们来看一下可以用于这一模式中的各种重要关键字：

<table>
	<tbody>
		<tr>
			<th>
				关键字
			</th>
			<th>
				描述
			</th>
		</tr>
		<tr>
			<td>
				$schema
			</td>
			<td>
				$schema 关键字状态，表示这个模式与 v4 规范草案书写一致。
			</td>
		</tr>
		<tr>
			<td>
				title
			</td>
			<td>
				用它给我们的模式提供了标题。
			</td>
		</tr>
		<tr>
			<td>
				description
			</td>
			<td>
				关于模式的描述。
			</td>
		</tr>
		<tr>
			<td>
				type
			</td>
			<td>
				type 关键字在我们的 JSON 数据上定义了第一个约束：必须是一个 JSON 对象。
			</td>
		</tr>
		<tr>
			<td>
				properties
			</td>
			<td>
				定义各种键和他们的值类型，以及用于 JSON 文件中的最小值和最大值。
			</td>
		</tr>
		<tr>
			<td>
				required
			</td>
			<td>
				存放必要属性列表。
			</td>
		</tr>
		<tr>
			<td>
				minimum
			</td>
			<td>
				给值设置的约束条件，表示可以接受的最小值。
				value.
			</td>
		</tr>
		<tr>
			<td>
				exclusiveMinimum
			</td>
			<td>
				如果存在 "exclusiveMinimum" 并且具有布尔值 true，如果它严格意义上大于 "minimum" 的值则实例有效。
			</td>
		</tr>
		<tr>
			<td>
				maximum
			</td>
			<td>
				给值设置的约束条件，表示可以接受的最大值。
			</td>
		</tr>
		<tr>
			<td>
				exclusiveMaximum
			</td>
			<td>
				如果存在 "exclusiveMinimum" 并且具有布尔值 true，如果它严格意义上小于 "minimum" 的值则实例有效。
			</td>
		</tr>
		<tr>
			<td>
				multipleOf
			</td>
			<td>
				如果通过这个关键字的值分割实例的结果是一个数字则表示紧靠 "multipleOf" 的数字实例是有效的。
			</td>
		</tr>
		<tr>
			<td>
				maxLength
			</td>
			<td>
				字符串实例字符的最大长度数值。
			</td>
		</tr>
		<tr>
			<td>
				minLength
			</td>
			<td>
				字符串实例字符的最小长度数值
			</td>
		</tr>
		<tr>
			<td>
				pattern
			</td>
			<td>
				如果正则表达式匹配实例成功则字符串实例被认为是有效的。
			</td>
		</tr>
	</tbody>
</table>

可以在 [http://json-schema.org](http://json-schema.org/latest/json-schema-validation.html) 上检出可用于定义 JSON 模式的完整关键字列表。上面的模式可用于测试下面给出的 JSON 代码的有效性：

```
[
	{
		"id": 2,
		"name": "An ice sculpture",
		"price": 12.50,
	},
	{
		"id": 3,
		"name": "A blue mouse",
		"price": 25.50,
	}
]
```

## JSON 与 XML 对比

JSON 和 XML 都是人类可读的格式并且与语言无关。在现实世界中它们都支持创建，读取和解码。我们可以基于以下因素来比较 JSON 和 XML：

### 冗余度

XML 比 JSON 冗余，因此对我们来说编写 JSON 会更快。

### 数组用法

XML 被用来描述结构化数据，不包含数组；而 JSON 包含数组。

### 解析

可以使用 JavaScript 的 eval 方法解析 JSON。当针对 JSON 应用这个方法时，eval 返回描述的对象。

### 示例

下面分别展示了一个 XML 和 JSON 示例：

__JSON：__

```
{
	"company": Volkswagen,
	"name": "Vento",
	"price": 800000
}
```

__XML：__

```
<car>
   <company>Volkswagen</company>
   <name>Vento</name>
   <price>800000</price>
</car>
```

## 在 PHP 中使用 JSON

本教程将会教我们如何使用 PHP 编程语言编码和解码 JSON 对象。下面我们先为 JSON 准备好 PHP 编程环境。

### 环境

从 PHP 5.2.0 开始默认捆绑了 JSON 扩展并被编译到 PHP 中。

### JSON 函数

<table>
	<tbody>
		<tr>
			<th>
				函数
			</th>
			<th>
				程序库
			</th>
		</tr>
		<tr>
			<td>
				json_encode
			</td>
			<td>
				返回一个值的 JSON 表示形式。
			</td>
		</tr>
		<tr>
			<td>
				json_decode
			</td>
			<td>
				解码为一个 JSON 字符串。
			</td>
		</tr>
		<tr>
			<td>
				json_last_error
			</td>
			<td>
				返回最后一次出现的错误。
			</td>
		</tr>
	</tbody>
</table>

### 使用 PHP 编码 JSON（json_encode）

PHP 的 json_encode() 函数用于在 PHP 中编码 JSON。编码成功时这个函数返回给定值的 JSON 表示形式，失败则返回 FALSE。

__语法：__

```
string json_encode ( $value [, $options = 0 ] )
```

__参数：__

- __value:__ 要编码的值。这个函数只能用于 UTF-8 编码的数据。
- __options:__ 这个可选值是一个由 JSON_HEX_QUOT, JSON_HEX_TAG, JSON_HEX_AMP, JSON_HEX_APOS, JSON_NUMERIC_CHECK,JSON_PRETTY_PRINT, JSON_UNESCAPED_SLASHES, JSON_FORCE_OBJECT 组成的位掩码。

__示例：__

下面的例子展示了如何使用 PHP 将一个数组转换为 JSON：

```
<?php
	$arr = array('a' => 1, 'b' => 2, 'c' => 3, 'd' => 4, 'e' => 5);
	echo json_encode($arr);
?>
```

执行时会生成如下结果：

```
{"a":1,"b":2,"c":3,"d":4,"e":5}
```

下面的例子展示了 PHP 对象也可以被转换为 JSON：

```
<?php
	class Emp {
		public $name = "";
		public $hobbies  = "";
		public $birthdate = "";
	}
	$e = new Emp();
	$e->name = "sachin";
	$e->hobbies  = "sports";
	$e->birthdate = date('m/d/Y h:i:s a', strtotime("8/5/1974 12:20:03"));

	echo json_encode($e);
?>
```

执行时会生成如下所示结果：

```
{"name":"sachin","hobbies":"sports","birthdate":"08\/05\/1974 12:20:03 pm"}
```

### 使用 PHP 解码 JSON（json_decode）

PHP 的 json-decode() 函数用于在 PHP 中解码 JSON。这个函数返回从 JSON 解码到适当 PHP 类型的值。

__语法：__

```
mixed json_decode ($json [,$assoc = false [, $depth = 512 [, $options = 0 ]]])
```

__参数：__

- __json_string:__ 编码的字符串，必须是 UTF-8 编码的数据。
- __assoc:__ 它是一个布尔类型的参数，当设置为 TRUE 时，返回的对象将会被转换为关联数组。
- __depth:__ 它是一个整型参数，用于指定递归深度。
- __options:__  它是一个 JSON 解码的整型位掩码。支持 JSON_BIGINT_AS_STRING。

__示例：__

下面例子展示了 如何使用 PHP 解码 JSON 对象：

```
<?php
	$json = '{"a":1,"b":2,"c":3,"d":4,"e":5}';

	var_dump(json_decode($json));
	var_dump(json_decode($json, true));
?>
```

执行时生成如下所示结果：

```
object(stdClass)#1 (5) {
	["a"] => int(1)
	["b"] => int(2)
	["c"] => int(3)
	["d"] => int(4)
	["e"] => int(5)
}

array(5) {
	["a"] => int(1)
	["b"] => int(2)
	["c"] => int(3)
	["d"] => int(4)
	["e"] => int(5)
}
```

## 在 Perl 中使用 JSON

本教程将会教我们如何使用 Perl 编程语言编码和解码 JSON 对象。新哦啊面我们先为 JSON 准备 Perl 编程环境。

### 环境

在开始使用 Perl 编码和解码 JSON 之前，我们需要安装 JSON 模块，可以从 CPAN 中获取。下载 JSON-2.53.tar.gz 或者其他任意最新版本之后遵循以下步骤：

```
$tar xvfz JSON-2.53.tar.gz
$cd JSON-2.53
$perl Makefile.PL
$make
$make install
```

### JSON 函数

<table>
	<thead>
		<tr>
			<th>函数</th>
			<th>程序库</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>encode_json</td>
			<td>将给定的 Perl 数据结构转为 UTF-8 编码的二进制字符串。</td>
		</tr>
		<tr>
			<td>decode_json</td>
			<td>解码 JSON 字符串。</td>
		</tr>
		<tr>
			<td>to_json</td>
			<td>将给定的 Perl 数据结构转换为 JSON 字符串。</td>
		</tr>
		<tr>
			<td>from_json</td>
			<td>接受一个 JSON 字符串并试图解析它，返回结果引用。</td>
		</tr>
		<tr>
			<td>convert_blessed</td>
			<td>给这个函数传递 true，则 Perl 可以使用这个对象类的 TO_JSON 方法将对象转换为 JSON。</td>
		</tr>
	</tbody>
</table>

### 使用 Perl 编码 JSON（encode_json）

Perl 的 encode_json() 函数可以将给定的 Perl 数据结构转换为 UTF-8 编码的二进制字符串。

__语法：__

```
$json_text = encode_json ($perl_scalar );
or
$json_text = JSON->new->utf8->encode($perl_scalar);
```

__示例：__

下面的例子展示了使用 Perl 将数组转换为 JSON：

```
#!/usr/bin/perl
use JSON;
my %rec_hash = ('a' => 1, 'b' => 2, 'c' => 3, 'd' => 4, 'e' => 5);
my $json = encode_json \%rec_hash;
print "$json\n";
```

执行时生成如下所示结果：

```
{"e":5,"c":3,"a":1,"b":2,"d":4}
```

下面的例子展示了如何将 Perl 对象转换为 JSON：

```
#!/usr/bin/perl
package Emp;
sub new
{
	my $class = shift;
	my $self = {
	name => shift,
		hobbies => shift,
		birthdate => shift,
	};
	bless $self, $class;
	return $self;
}
sub TO_JSON { return { %{ shift() } }; }

package main;
use JSON;
my $JSON = JSON->new->utf8;
$JSON->convert_blessed(1);

$e = new Emp( "sachin", "sports", "8/5/1974 12:20:03 pm");
$json = $JSON->encode($e);
print "$json\n";
```

执行时生成如下所示结果：

```
{"birthdate":"8/5/1974 12:20:03 pm","name":"sachin","hobbies":"sports"}
```

### 使用 Perl 解码 JSON（decode_json）

Perl 的 decode_json() 函数用于在 Perl 中解码 JSON。这个函数返回从 JSON 解码到适当 Perl 类型的值。

__语法：__

```
$perl_scalar = decode_json $json_text
or
$perl_scalar = JSON->new->utf8->decode($json_text)
```

__示例：__

下面的例子展示了如何使用 Perl 解码 JSON 对象。如果你的机器上没有 Data::Dumper 模块那么你需要安装这个模块。

```
#!/usr/bin/perl
use JSON;
use Data::Dumper;

$json = '{"a":1,"b":2,"c":3,"d":4,"e":5}';

$text = decode_json($json);
print Dumper($text);
```

执行时生成如下所示结果：

```
$VAR1 = {
	'e' => 5,
	'c' => 3,
	'a' => 1,
	'b' => 2,
	'd' => 4
};
```

## 在 Python 中使用 JSON

本教程将会教我们如何使用 Python 编程语言编码和解码 JSON。下面我们先为 JSON 准备好 Python 编程环境。

### 环境

在我们使用 Python 编码和解码 JSON 之前，我们需要安装一个可用 JSON 模块。对于本教程请按照如下方式下载和安装 [Demjson](http://deron.meranda.us/python/demjson/)：

```
$tar xvfz demjson-1.6.tar.gz
$cd demjson-1.6
$python setup.py install
```

### JSON 函数

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

### 使用 Python 编码 JSON（encode）

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

### 使用 Python 解码 JSON（decode）

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

## 在 Ruby 中使用 JSON

本教程将会教我们如何使用 Ruby 编程语言编码和解码 JSON。下面我们先为 JSON 准备好 Ruby 编程环境。

### 环境

在我们使用 Ruby 编码和解码 JSON 之前，我们需要安装一个可用于 Ruby 的 JSON 模块。你可能需要安装 Ruby gem，如果你使用的是最新版的 Ruby，那么你必须在你的机器上安装 gem，安装好 gem 之后遵循下面这个步骤：

```
$gem install json
```

### 使用 Ruby 解析 JSON

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

## 在 Java 中使用 JSON

本教程将会教我们如何使用 Java 编程语言编码和解码 JSON。下面我们先为 JSON 准备好 Java 编程环境。

### 环境

在我们使用 Java 编码和解码 JSON 之前，我们需要安装一个可用的 JSON 模块。对于这个教程请下载和安装 [JSON.simple](https://code.google.com/p/json-simple/)，然后把 __jsonsimple-1.1.1.jar__ 文件的路径添加到环境变量 CLASSPATH 中。

### JSON 和 Java 实体映射

JSON.simple 实体映射从左侧到右侧为解码或解析，实体映射从右侧到左侧为编码。

<table>
	<thead>
		<tr>
			<th>JSON</th>
			<th>Java</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>string</td>
			<td>java.lang.String</td>
		</tr>
		<tr>
			<td>number</td>
			<td>java.lang.Number</td>
		</tr>
		<tr>
			<td>true | false</td>
			<td>java.lang.Boolean</td>
		</tr>
		<tr>
			<td>null</td>
			<td>null</td>
		</tr>
		<tr>
			<td>array</td>
			<td>java.util.List</td>
		</tr>
		<tr>
			<td>object</td>
			<td>java.util.Map</td>
		</tr>
	</tbody>
</table>

解码时，_java.util.List_的默认具体类是_org.json.simple.JSONArray_，_java.util.Map_的默认具体类是_org.simple.JSONObject_。

### 在 Java 中编码 JSON

下面这个简单的示例展示了使用 java.util.HashMap 的子类 JSONObject 编码一个 JSON 对象。这里并没有提供顺序。如果你需要严格的元素顺序，请使用 JSONValue.toJSONString(map) 方法的有序映射实现，比如 java.util.LinkedHashMap。

```
import org.json.simple.JSONObject;

class JsonEncodeDemo 
{
	public static void main(String[] args)
	{
		JSONObject obj = new JSONObject();

		obj.put("name", "foo");
		obj.put("num", new Integer(100));
		obj.put("balance", new Double(1000.21));
		obj.put("is_vip", new Boolean(true));

		System.out.print(obj);
	}
}
```

编译和执行上面的程序时，会生成如下所示结果：

```
{"balance": 1000.21, "num":100, "is_vip":true, "name":"foo"}
```

下面是另一个示例，使用 Java JSONObject 展示了 JSON 对象流：

```
import org.json.simple.JSONObject;
class JsonEncodeDemo
{
	public static void main(String[] args)
	{
		JSONObject obj = new JSONObject();

		obj.put("name","foo");
		obj.put("num",new Integer(100));
		obj.put("balance",new Double(1000.21));
		obj.put("is_vip",new Boolean(true));

		StringWriter out = new StringWriter();
		obj.writeJSONString(out);
		String jsonText = out.toString();
		System.out.print(jsonText);
	}
}
```

编译和执行上面的程序时，会生成如下所示结果：

```
{"balance": 1000.21, "num":100, "is_vip":true, "name":"foo"}
```

### 在 Java 中解码 JSON

下面的例子使用了 __JSONObject__ 和 __JSONArray__，其中 JSONObject 就是 java.util.Map，JSONArray 就是 java.util.List，因此我们可以使用 Map 或 List 的标准操作访问它们。

```
import org.json.simple.JSONObject;
import org.json.simple.JSONArray;
import org.json.simple.parser.ParseException;
import org.json.simple.parser.JSONParser;

class JsonDecodeDemo
{
	public static void main(String[] args)
	{
		JSONParser parser=new JSONParser();
		String s = "[0,{\"1\":{\"2\":{\"3\":{\"4\":[5,{\"6\":7}]}}}}]";
			try{
			Object obj = parser.parse(s);
			JSONArray array = (JSONArray)obj;
			System.out.println("The 2nd element of array");
			System.out.println(array.get(1));
			System.out.println();
			JSONObject obj2 = (JSONObject)array.get(1);
			System.out.println("Field \"1\"");
			System.out.println(obj2.get("1"));

			s = "{}";
			obj = parser.parse(s);
			System.out.println(obj);

			s= "[5,]";
			obj = parser.parse(s);
			System.out.println(obj);

			s= "[5,,2]";
			obj = parser.parse(s);
			System.out.println(obj);
		}catch(ParseException pe){
			System.out.println("position: " + pe.getPosition());
			System.out.println(pe);
		}
	}
}
```

编译和执行上面的程序时，会生成如下所示结果：

```
The 2nd element of array
{"1":{"2":{"3":{"4":[5,{"6":7}]}}}}

Field "1"
{"2":{"3":{"4":[5,{"6":7}]}}}
{}
[5]
[5,2]
```

## JSON 与 Ajax

AJAX 就是异步 JavaScript 和 XML，它是一组在客户端创建异步 Web 应用程序的相互关联的 Web 开发技术。遵循 AJAX 模型，Web 应用程序以异步分方式发送数据和从服务器上接受获取数据，从而不影响现有页面的显示行为。

许多开发人员都在客户端和服务器之间使用 JSON 传递 AJAX 更新。实时更新体育成绩的站点就可以视为一个 AJAX 例子。如果这些成绩要更新到站点上，那么必须要把它们存储到服务器上便于需要时网页能取回这些成绩。这里我们可以使用 JSON 格式的数据。

任何使用 AJAX 更新的数据都可以使用 JSON 格式存储在 Web 服务器上。使用 AJAX，那么 JavaScript 就可以在必要时取回这些 JSON 文件，解析它们，然后做以下两件事情：

- 把它们显示到网页上之前将解析的值存储到变量中便于进一步处理。
- 直接分配数据给网页中的 DOM 元素，那么它就会显示在站点上。

### 示例

下面的代码展示了 JSON 和 AJAX，请把它们保存为 __ajax.htm__ 文件。这里的加载函数 loadJSON() 将会使用异步的方式上传 JSON 数据。

```
<head>
<meta content="text/html; charset=ISO-8859-1" http-equiv="content-type">
<script type="application/javascript">
function loadJSON()
{
	var data_file = "http://www.tutorialspoint.com/json/data.json";
	var http_request = new XMLHttpRequest();
	try{
		// Opera 8.0+, Firefox, Chrome, Safari
		http_request = new XMLHttpRequest();
	}catch (e){
		// IE 浏览器处理
		try{
			http_request = new ActiveXObject("Msxml2.XMLHTTP");
		}catch (e) {
			try{
				http_request = new ActiveXObject("Microsoft.XMLHTTP");
			}catch (e){
				// 错误处理
				alert("Your browser broke!");
				return false;
			}
		}
	}
	http_request.onreadystatechange = function(){
		if (http_request.readyState == 4 )
		{
			// 使用 JSON.parse 解析 JSON 数据
			var jsonObj = JSON.parse(http_request.responseText);
			// jsonObj 变量现在包含数组结构，可以通过 jsonObj.name 和 jsonObj.country 的方式访问
			document.getElementById("Name").innerHTML = jsonObj.name;
			document.getElementById("Country").innerHTML = jsonObj.country;
		}
	}
	http_request.open("GET", data_file, true);
	http_request.send();
}
</script>
<title>tutorialspoint.com JSON</title>
</head>
<body>
<h1>Cricketer Details</h1>
<table class="src">
<tr><th>Name</th><th>Country</th></tr>
<tr><td><div id="Name">Sachin</div></td>
<td><div id="Country">India</div></td></tr>
</table>
<div class="central">
<button type="button" onclick="loadJSON()">Update Details </button>
</body>
</html>
```

下面就是包含 JSON 格式数据的输入文件 __data.json__，当我们点击 __Update Detail__ 按钮时会以异步的方式上传它。这个文件已经保存到 [http://www.tutorialspoint.com/json/](http://www.tutorialspoint.com/json/) 上了。

```
{"name": "brett", "country": "Australia"}
```

上面的 HTML 代码会生成如下所示屏幕显示，这里你可以进行 AJAX 实战：

![ajax in action](images/ajax-in-action1.png)

当我们点击 __Update Detail__ 按钮式，应该会得到如下所示的结果，我们可以自己尝试 JSON 和 AJAX，提供自己的浏览器支持的 JavaScript。

![ajax in action](images/ajax-in-action2.png)