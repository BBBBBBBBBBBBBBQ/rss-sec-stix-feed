# 订阅数据格式

## STIX 文件

`bundle.json` 是一个 JSON 对象，顶层包含 `type`（固定为 `bundle`）、`id` 和 `objects` 数组。数组中的对象通过 `id` 相互引用。[下载 bundle.json](https://raw.githubusercontent.com/BBBBBBBBBBBBBBQ/rss-sec-stix-feed/main/bundle.json)

| 对象类型 | 主要字段及含义 |
| --- | --- |
| `report` | `name` 为标题，`description` 为中文研判，`published` 为发布时间。`external_references` 列出来源名称和原文链接，`object_refs` 列出报告引用的对象 ID。 |
| `indicator` | `pattern` 保存 IOC 的匹配表达式，`valid_from` 为生效时间，`valid_until` 在已知时给出。 |
| `file` | `hashes` 按算法名称保存文件哈希值。 |
| `domain-name`、`ipv4-addr`、`ipv6-addr`、`url` | `value` 保存对应的域名、IP 地址或 URL。 |
| `relationship` | `relationship_type` 为 `based-on` 时，`source_ref` 指向 Indicator，`target_ref` 指向其匹配的可观测对象。 |
| `vulnerability`、`attack-pattern`、`identity` | 分别表示 CVE 漏洞、ATT&CK 技术和机构。 |

报告同时引用 Indicator、对应的可观测对象和连接两者的关系。报告与 Indicator 的标签位于 `labels`，可观测对象的标签位于 `x_opencti_labels`。`source:*` 表示来源，`t:*` 表示主题。

## RSS 文件

`feed.xml` 中每个 `channel/item` 对应一份报告，可用 `guid` 与 STIX 文件中的 `report.id` 对照。[下载 feed.xml](https://raw.githubusercontent.com/BBBBBBBBBBBBBBQ/rss-sec-stix-feed/main/feed.xml)

| 字段 | 含义 |
| --- | --- |
| `guid` | 报告的 STIX ID |
| `title` | 报告标题 |
| `link` | 首个来源的原文链接 |
| `pubDate` | 报告发布时间 |
| `category` | 报告标签，每个标签对应一个元素 |
| `description` | HTML 格式的中文研判正文 |
