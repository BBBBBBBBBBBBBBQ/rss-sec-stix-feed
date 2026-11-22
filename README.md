# RSS Security Intelligence

公开订阅提供两种固定地址，均可匿名读取。

| 使用方式 | 地址 | 在 OpenCTI 6.9.19 中的效果 |
|---|---|---|
| STIX 2.1 | [bundle.json](https://raw.githubusercontent.com/BBBBBBBBBBBBBBQ/rss-sec-stix-feed/main/bundle.json) | 通过支持静态 Bundle 的连接器导入报告、指标、CVE、ATT&CK 技术及报告引用。按对象 ID 和版本接收修订。 |
| RSS 2.0 | [feed.xml](https://raw.githubusercontent.com/BBBBBBBBBBBBBBQ/rss-sec-stix-feed/main/feed.xml) | 在 **Data → Ingestion → RSS Feeds** 粘贴链接。报告正文在条目的 description 中，原生订阅按发布时间读取新报告。 |

中文事件报告覆盖最近 14 个日历日的日报重点。详细版利用公开来源文章的归档制作，保留有段落依据的时间线、影响范围、归因判断、检测线索和修复信息。每项新增判断后的序号指向报告末尾的原始来源；有可识别小节时附上章节名。来源缺少可用正文时保留日报摘要。

厂商部分选取最近最多 10 份归档完整、明确标为 TLP:CLEAR 或 TLP:WHITE 的 Cisco Talos 报告。报告附有可导入的检测指标、厂商标注的技术及原始文件引用。时间字段中，报告的 `published` 表示报告发布时间，指标的 `valid_from` 表示其生效时间。

订阅每四小时检查更新。GitHub 提供静态文件下载；OpenCTI 的 TAXII Feed 设置需要另外提供 TAXII 服务的 API Root 和 Collection。[OpenCTI 6.9 RSS 说明](https://docs.opencti.io/6.9.X/usage/import/rss-feed/) · [TAXII Feed 说明](https://docs.opencti.io/6.9.X/usage/import/taxii-feed/)
