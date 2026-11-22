# RSS Security Intelligence

匿名订阅地址为 [STIX 2.1 Bundle](https://raw.githubusercontent.com/BBBBBBBBBBBBBBQ/rss-sec-stix-feed/main/bundle.json)。

报告提供中文事件摘要、影响、防御建议、证据来源链接及 CVE。厂商 IOC 报告保留 Cisco Talos 发布的检测值和 ATT&CK 技术引用。日报覆盖最近 14 个日历日，Talos 部分选取最近最多 10 份已明确标为 TLP:CLEAR 或 TLP:WHITE 的可解析报告。对象的原始情报时间见报告的 `published` 和指标的 `valid_from`。

订阅文件每四小时检查更新。消费者可用对象的 `id` 和 `modified` 识别新增或修订。OpenCTI 可通过轮询静态 STIX Bundle 的外部连接器接入，也可下载文件后用 ImportFileStix 导入。每份报告的 `external_references` 指向原始来源，`object_refs` 指向相关实体。
