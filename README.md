# Siteation Experiment - Magento 2 Cross Document View Transitions

This project explores the Cross Document View Transitions API to create smooth and visually appealing transitions between views within your Magento 2 store.

By leveraging this experimental browser feature (currently only available in Chrome),
you can enhance user engagement and provide a more delightful shopping experience.

> [!WARNING]
> **Important Note:** As the View Transitions API is still under development,
> this code is for experimentation only and should not be deployed on a production site.

![preview](./assets/magento-view-transition.gif)

## Try it your self

1. **Enable Chrome Flag:** Open Chrome and navigate to `chrome://flags/#view-transition-on-navigation`. Locate the "viewTransition API for navigations" flag and set it to "Enabled."

2. **Include CSS:** Add the following CSS to your main CSS file to enable view transitions for navigation (and disable them for users with reduced motion preferences).

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

3. **Apply Inline Styles:** Create smooth product image transitions by adding the following inline styles to each product list item and the main product gallery section:

**Product List Item:**

```php
style="view-transition-name: product-<?= $productId ?>"
```

**Main Product Gallery:**

```php
style="view-transition-name: product-<?= $block->getProduct()->getId() ?>"
```

**Experiment, Explore, and Refine**

This example demonstrates the basic setup for cross-document view transitions using the View Transitions API. 

You can experiment with different animation properties (like `duration`, `timing-function`, etc.) within your CSS to refine the transition behavior and create a unique experience for your store.

**Additional Resources**

- Introduction to View Transitions: [https://developer.chrome.com/docs/web-platform/view-transitions](https://developer.chrome.com/docs/web-platform/view-transitions)
- Explainer for Cross Document View Transitions: [https://github.com/WICG/view-transitions/blob/main/cross-doc-explainer.md](https://github.com/WICG/view-transitions/blob/main/cross-doc-explainer.md)
- CSSWG View Transitions Documentation: [https://developer.mozilla.org/en-US/docs/Web/API/ViewTransition](https://developer.mozilla.org/en-US/docs/Web/API/ViewTransition)

**Disclaimer:** Remember that this is an experimental feature, and browser support might change in the future. Consider using feature detection or polyfills if you plan to integrate this into a production environment.
