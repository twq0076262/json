# 在 Java 中使用 JSON

本教程将会教我们如何使用 Java 编程语言编码和解码 JSON。下面我们先为 JSON 准备好 Java 编程环境。

## 环境

在我们使用 Java 编码和解码 JSON 之前，我们需要安装一个可用的 JSON 模块。对于这个教程请下载和安装 [JSON.simple](https://code.google.com/p/json-simple/)，然后把 __jsonsimple-1.1.1.jar__ 文件的路径添加到环境变量 CLASSPATH 中。

## JSON 和 Java 实体映射

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

## 在 Java 中编码 JSON

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
java
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

## 在 Java 中解码 JSON

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