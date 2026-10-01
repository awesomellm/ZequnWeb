# 事例：表示内容と多言語メタデータの対応

[English](MULTILINGUAL-CASE.md) | [简体中文](MULTILINGUAL-CASE.zh-CN.md) | [日本語](MULTILINGUAL-CASE.ja.md) | [繁體中文](MULTILINGUAL-CASE.zh-HK.md)

2026年9月10日の ZequnWeb の過去の確認では、繁体字の実績ページに八件が表示されていた一方、構造化リストは同じ内容になっていませんでした。表示カードと構造化リストを同じデータから生成するように修正しました。最終記録は繁体字八件、英語と簡体字は各十六件です。

## 修正内容

更新日は共通の解析処理から取得し、構造化メタデータとサイトマップが記録された内容変更日を示すようにしました。日付抽出は回帰テストで確認しています。代替言語は実際の翻訳ページと照合しました。言語ラベルがあるだけでは対応する翻訳の存在は示せません。

これは整合性の修正です。検索への登録や事業成果の改善を証明しません。[過去の証拠記録](implementation-evidence.json) は196個のHTML、197件の生成処理、三件の日付テストと、ローカルのSEO・構造・内部リンク検査の合格を記録しています。公開日は2026年9月12日で、当時の出力を説明し、現在の公開環境を示すものではありません。

## 手順を再利用する

1. ページに固定の識別子を与え、翻訳タイトルやURLと分けて管理します。
2. 承認された同じ記録から表示リストと構造化リストを作ります。
3. 自己参照の正規URLと実在する同等の言語ページ、相互参照を出力します。
4. 静的出力を生成し、HTML、サイトマップ、各言語のリンクを確認します。
5. 版、日付、ページ数、確認範囲を記録して結果を説明します。

[実行可能なサイト例](https://github.com/awesomellm/multilingual-website-starter/blob/main/README.ja.md) は四言語と三種類の同等ページを示します。[静的検査ツール](https://github.com/awesomellm/website-seo-checker/blob/main/README.ja.md) は手順の一部を確認します。翻訳の正確さと実際のサーバー応答は別途確認してください。[言語対応表](https://github.com/awesomellm/website-migration-kit/blob/main/multilingual-content-map.ja.csv) で担当者と不足する翻訳を管理できます。
