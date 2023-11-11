# Siteation Experiment - Magento 2 View Transitions

## Spec Explainer

- Intro to view transitions: https://developer.chrome.com/docs/web-platform/view-transitions/
- Explainer for cross doc: https://github.com/WICG/view-transitions/blob/main/cross-doc-explainer.md
- Issue for cross doc support: https://github.com/w3c/csswg-drafts/issues/8804
- CSSWG doc: https://drafts.csswg.org/css-view-transitions-2/

## Try your self

![preview](./assets/magento-view-transition.gif)

<!-- TODO -->

```xml
<?xml version="1.0"?>
<page xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:noNamespaceSchemaLocation="urn:magento:framework:View/Layout/etc/page_configuration.xsd">
    <head>
        <meta name="view-transition" content="same-origin"/>
    </head>
</page>
```

<!-- PLP: `style="view-transition-name: product-<?= $productId ?>"` -->
<!-- PDP: `style="view-transition-name: product-<?= $block->getProduct()->getId() ?>"` -->
