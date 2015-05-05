# 在 PHP 中使用 JSON

本教程将会教我们如何使用 PHP 编程语言编码和解码 JSON 对象。下面我们先为 JSON 准备好 PHP 编程环境。

## 环境

从 PHP 5.2.0 开始默认捆绑了 JSON 扩展并被编译到 PHP 中。

## JSON 函数

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

## 使用 PHP 编码 JSON（json_encode）

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

## 使用 PHP 解码 JSON（json_decode）

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