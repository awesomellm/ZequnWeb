# Image delivery case: smaller referenced assets

[English](IMAGE-DELIVERY-CASE.md) | [简体中文](IMAGE-DELIVERY-CASE.zh-CN.md) | [日本語](IMAGE-DELIVERY-CASE.ja.md) | [繁體中文](IMAGE-DELIVERY-CASE.zh-HK.md)

On 30 September 2026, a local ZequnWeb production export replaced a large shared logo with a hashed WebP asset, generated multiple artwork sizes, and supplied `srcset`, `sizes` and intrinsic dimensions. The recorded changes below measure referenced file sizes. That record says the source and export were updated but the changes had not yet been deployed.

| Metric | Before (bytes) | After (bytes) | Change |
| --- | ---: | ---: | ---: |
| Largest shared logo | 265,115 | 6,836 | −97.4% |
| Homepage referenced JavaScript | 787,479 | 674,140 | −14.4% |
| Homepage referenced CSS | 280,232 | 256,906 | −8.3% |
| Local JavaScript gzip estimate | 240,564 | 203,209 | −15.5% |
| Local CSS gzip estimate | 52,086 | 46,787 | −10.2% |

## Verify the actual selection

In a 390-pixel browser viewport, the test selected a 96-pixel logo of 3,244 bytes and a 480-pixel hero image of 16,362 bytes. The hero retained loading priority; decorative and portfolio images used lazy loading. Added trade-demo functionality increased that page's JavaScript by 1.9% and CSS by 2.0%, so the record does not say every page became smaller.

Intrinsic dimensions need compatible CSS. After dimensions were added, a Traditional Chinese portfolio rule that changed width but left the original HTML height distorted cards. Adding `height: auto` restored the intended ratio; desktop and mobile views were checked again.

## Reproduce a defensible comparison

Record the input asset, generated widths and formats, rendered `sizes`, selected `currentSrc`, natural dimensions, file bytes, viewport and export revision. Compare the same route and conditions. Keep the hero eager where justified and defer noncritical images. Review visual quality and layout after changing formats or dimensions.

The [localized evidence table](image-evidence.csv) preserves these historical numbers. Local gzip totals exclude runtime third-party scripts and do not measure actual CDN transfer, Core Web Vitals, rankings or conversions. Measure deployed network and field behavior separately before making those claims.
