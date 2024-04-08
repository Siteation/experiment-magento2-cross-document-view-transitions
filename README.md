# Siteation Experiment - Magento 2 View Transitions

<!-- TODO: intro -->

## Spec Explainer

- Intro to view transitions: https://developer.chrome.com/docs/web-platform/view-transitions/
- Explainer for cross doc: https://github.com/WICG/view-transitions/blob/main/cross-doc-explainer.md
- Issue for cross doc support: https://github.com/w3c/csswg-drafts/issues/8804
- CSSWG doc: https://drafts.csswg.org/css-view-transitions-2/

## Try your self

![preview](./assets/magento-view-transition.gif)

Add the following CSS to your main CSS file.

```css
@view-transition {
   navigation: auto;
}

@media (prefers-reduced-motion) {
  @view-transition {
    navigation: none;
  }
}
```

And for the nice transition of the product image make sure to add the following inline styles to each list item:

```php
style="view-transition-name: product-<?= $productId ?>"
```

and to the mian product gallery:

```php
style="view-transition-name: product-<?= $block->getProduct()->getId() ?>"
```
