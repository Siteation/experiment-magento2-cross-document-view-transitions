# Siteation Experiment - Magento 2 Cross Document View Transitions

This project explores the Cross Document View Transitions API to create smooth and visually appealing transitions between views within your Magento 2 store.

By leveraging this experimental browser feature (currently only available in Chrome),
you can enhance user engagement and provide a more delightful shopping experience.

![preview](./assets/magento-view-transition.gif)

## Try it your self

1. **Include CSS:** Add the following CSS to your main CSS file to enable view transitions for navigation (and disable them for users with reduced motion preferences).

   ```css
   @view-transition {
     navigation: auto;
   }
   ```

2. **Apply Inline Styles:** Create smooth product image transitions by adding the following inline styles to each product list item and the main product gallery section:

   **Product List Item:**

   ```php
   style="view-transition-name: product-<?= $productId ?>"
   ```

   **Main Product Gallery:**

   ```php
   style="view-transition-name: product-<?= $block->getProduct()->getId() ?>"
   ```

## Experiment, Explore, and Refine

This example demonstrates the basic setup for cross-document view transitions using the View Transitions API. 

You can experiment with different animation properties (like `duration`, `timing-function`, etc.) within your CSS to refine the transition behavior and create a unique experience for your store.

## Additional Resources

- Introduction to View Transitions: https://developer.chrome.com/docs/web-platform/view-transitions
- Explainer for Cross Document View Transitions: https://github.com/WICG/view-transitions/blob/main/cross-doc-explainer.md
- CSSWG View Transitions Documentation: https://developer.mozilla.org/en-US/docs/Web/API/ViewTransition
- Google IO Talk: https://youtu.be/eY6C_-aDdTo?si=quYRCJ3M9446ZMlx
- Chrome Release 126 article: https://developer.chrome.com/blog/new-in-chrome-126#cross-document-transitions
- Chrome Docs on cross-document view-transitions: https://developer.chrome.com/docs/web-platform/view-transitions/cross-document

**Disclaimer:** Remember that this is an experimental feature, and browser support might change in the future. Consider using feature detection or polyfills if you plan to integrate this into a production environment.
