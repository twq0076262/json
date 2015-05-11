# JSON 与 XML 对比

JSON 和 XML 都是人类可读的格式并且与语言无关。在现实环境中它们都支持创建，读取和解码。我们可以基于以下因素来比较 JSON 和 XML：

## 冗余度

XML 比 JSON 冗余，因此对我们来说编写 JSON 会更快。

## 数组用法

XML 被用来描述结构化数据，不包含数组；而 JSON 包含数组。

## 解析

可以使用 JavaScript 的 eval 方法解析 JSON。当针对 JSON 应用这个方法时，eval 返回描述的对象。

## 示例

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