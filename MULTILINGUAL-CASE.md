# Case: matching visible content and multilingual metadata

[English](MULTILINGUAL-CASE.md) | [简体中文](MULTILINGUAL-CASE.zh-CN.md) | [日本語](MULTILINGUAL-CASE.ja.md) | [繁體中文](MULTILINGUAL-CASE.zh-HK.md)

A historical ZequnWeb check on 10 September 2026 found that the Traditional Chinese portfolio displayed eight items while its structured list did not match that visible set. The repair used one data source for the visible cards and the structured list. The final recorded Traditional Chinese list contained eight items; the English and Simplified Chinese lists each contained sixteen.

## What changed

Content modification dates were also derived through a shared parser, so structured metadata and sitemap dates referred to the actual recorded content change. Regression tests covered the date extraction. Language alternatives were reviewed against actual translated pages: a language label alone did not establish that a corresponding translation existed.

These are consistency repairs. They do not show that a search engine indexed a page or that business results improved. The [historical evidence record](implementation-evidence.json) records 196 checked HTML files, 197 generation tasks, three date-regression tests, and passing local SEO, structure and internal-link checks. It was published on 12 September 2026 and describes that historical export, not today's live deployment.

## Repeat the procedure

1. Assign a stable identity to each page, separate from its translated title and URL.
2. Render visible lists and corresponding structured lists from the same approved records.
3. Emit self canonicals and real equivalent-page language alternatives, including reciprocal references.
4. Build the export, inspect the resulting HTML and sitemap, and check links in each language.
5. Record the revision, date, page counts and limitations before describing the result.

The [runnable starter](https://github.com/awesomellm/multilingual-website-starter/blob/main/README.md) demonstrates four languages and three equivalent page identities. The [static checker](https://github.com/awesomellm/website-seo-checker/blob/main/README.md) verifies part of this procedure. Translation accuracy and real server responses still require review. Use the [language content map](https://github.com/awesomellm/website-migration-kit/blob/main/multilingual-content-map.csv) to track ownership and missing equivalents.
