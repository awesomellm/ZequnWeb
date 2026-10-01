# 案例：让可见内容与多语言元数据对应

[English](MULTILINGUAL-CASE.md) | [简体中文](MULTILINGUAL-CASE.zh-CN.md) | [日本語](MULTILINGUAL-CASE.ja.md) | [繁體中文](MULTILINGUAL-CASE.zh-HK.md)

ZequnWeb 在 2026 年 9 月 10 日的历史检查中发现，繁体作品页可见八个项目，但结构化列表没有对应同一组内容。修复改用同一数据源生成作品卡片和结构化列表。最终记录中，繁体列表为八项；英文和简体列表各为十六项。

## 修改内容

内容修改日期也改由共享解析器取得，让结构化元数据和网站地图指向实际记录的内容修改时间，并用回归测试覆盖日期提取。语言版本按照真正存在的译文页面检查：有语言标签不代表已经有相应译文。

这是内容一致性修复，不代表搜索引擎已收录或业务效果提高。[历史证据记录](implementation-evidence.json) 记载检查了 196 个 HTML、197 项生成任务、三项日期回归测试，且本地 SEO、结构和内部链接检查通过。记录于 2026 年 9 月 12 日公开，说明当时的静态导出，不代表当前线上状态。

## 复用步骤

1. 为每个页面分配稳定身份，与翻译后的标题和网址分开管理。
2. 用同一组已确认记录生成可见列表和相应结构化列表。
3. 输出自身规范地址及真正对应的语言页面，包含相互返回关系。
4. 构建静态导出，检查生成的 HTML、网站地图及每种语言的链接。
5. 记录版本、日期、页面数和范围，再描述验证结果。

[可运行网站示例](https://github.com/awesomellm/multilingual-website-starter/blob/main/README.zh-CN.md) 展示四语言、三种相同页面身份；[静态检查器](https://github.com/awesomellm/website-seo-checker/blob/main/README.zh-CN.md) 验证其中一部分。翻译准确性及真实服务器响应仍须审查。用[语言内容对应表](https://github.com/awesomellm/website-migration-kit/blob/main/multilingual-content-map.zh-CN.csv) 管理负责人及缺少的译文。
