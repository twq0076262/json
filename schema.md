# JSON 模式（Schema）

JSON 模式是一种基于 JSON 格式定义 JSON 数据结构的规范。它被写在 IETF 草案下并于 2011 年到期。JSON 模式：

- 描述现有数据格式。
- 干净的人类和机器可读的文档。
- 完整的结构验证，有利于自动化测试。
- 完整的结构验证，可用于验证客户端提交的数据。

## JSON 模式验证库

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

## JSON 模式示例

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