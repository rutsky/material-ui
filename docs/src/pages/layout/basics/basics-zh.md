# 基础布局

<p class="description">Material Design布局鼓励通过统一的元素和间隔来实现跨平台、环境、屏幕尺寸的一致性。</p>

## 响应式UI

Material Design中的[响应式布局](https://material.io/design/layout/responsive-layout-grid.html)可适配任何可能的屏幕尺寸。 我们提供以下工具以实现响应式UI：

- [Grid](/layout/grid/): The grid creates visual consistency between layouts while allowing flexibility across a wide variety of designs.

- [Hidden](/layout/hidden/): The hidden component can be used to change the visibility of the elements.

- [Breakpoints](/layout/breakpoints/): We provide a low-level API for using the breakpoints in a wide variery of context.

## z-index

Several Material-UI components utilize `z-index`, the CSS property that helps control layout by providing a third axis to arrange content. We utilize a default z-index scale in Material-UI that's been designed to properly layer drawers, modals, snackbars, tooltips, and more.

[These values](https://github.com/mui-org/material-ui/blob/master/packages/material-ui/src/styles/zIndex.js) start at an arbitrary number, high and specific enough to ideally avoid conflicts.

- mobile stepper: 1000
- app bar: 1100
- drawer: 1200
- modal: 1300
- snackbar: 1400
- tooltip: 1500

These values can always be customized. You will find them in the theme under the [`zIndex`](/customization/default-theme/?expend-path=$.zIndex) key. We don’t encourage customization of individual values; should you change one, you likely need to change them all.