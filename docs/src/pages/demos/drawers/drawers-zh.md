---
title: React Paper 组件
components: Drawer, SwipeableDrawer
---
# 抽屉

<p class="description">导航抽屉可以访问您应用中的地址。侧栏是包含附加内容的平面，它固定在屏幕的左侧或右侧。</p>

[Navigation drawers](https://material.io/design/components/navigation-drawer.html) 提供对目标和应用功能 如切换帐户 的访问。 它们可以是永久在屏幕上或由导航菜单图标控制。

[Side sheets](https://material.io/design/components/sheets-side.html) 主要用于平板电脑和台式机的辅助平面。

## 临时抽屉

临时导航抽屉可以打开或关闭。默认情况下关闭，抽屉打开会暂时在所有其他内容之上，直到选择一个部分。

单击或者按Esc键可以关闭抽屉。当选择抽屉中的一项时，它也会关闭，通过操作 `open` prop来处理。

{{"demo": "pages/demos/drawers/TemporaryDrawer.js", "hideEditButton": true}}

## 可滑动的临时抽屉

您可以使用 `SwipeableDrawer` 组件滑动抽屉。

此组件附带 2 kB gzip 的负载开销。 一些低端移动设备无法以 60 FPS 的速度跟随手指。 您可以使用 `disableBackdropTransition` 属性来提供帮助。

{{"demo": "pages/demos/drawers/SwipeableTemporaryDrawer.js", "hideEditButton": true}}

我们网站上的文档使用以下属性来获得组件的最佳可用性: -iOS 托管于高端设备上。 我们可以在不丢帧的情况下启用背景转换。 它的表现将十分优秀。 -iOS 有一个"滑动返回"的功能，它与组件冲突。 我们必须禁用它。

```jsx
const iOS = process.browser && /iPad|iPhone|iPod/.test(navigator.userAgent);

<SwipeableDrawer disableBackdropTransition={!iOS} disableDiscovery={iOS} />
```

## 永久抽屉

永久抽屉始终可见并固定在左侧，与内容或背景位于同一高度。他们无法被关闭。

永久抽屉是桌面</strong> 推荐的默认值**。</p> 

### 全高度导航栏

应用程序侧重与从左到右层次结构的信息消费。

{{"demo": "pages/demos/drawers/PermanentDrawer.js", "hideEditButton": true}}

### Clipped under the app bar

Apps focused on productivity that require balance across the screen.

{{"demo": "pages/demos/drawers/ClippedDrawer.js", "hideEditButton": true}}

## 持久抽屉

持久抽屉可以打开或关闭。 抽屉与内容位于同一表面的高度上。 它默认情况下是关闭的，可通过选择菜单图标打开，它会保持打开状态，直到用户关闭。 The state of the drawer is remembered from action to action and session to session.

When the drawer is outside of the page grid and opens, the drawer forces other content to change size and adapt to the smaller viewport.

Persistent navigation drawers are acceptable for all sizes larger than mobile. They are not recommended for apps with multiple levels of hierarchy that require using an up arrow for navigation.

{{"demo": "pages/demos/drawers/PersistentDrawer.js", "hideEditButton": true}}

## Mini variant drawer

In this variation, the persistent navigation drawer changes its width. Its resting state is as a mini-drawer at the same elevation as the content, clipped by the app bar. When expanded, it appears as the standard persistent navigation drawer.

The mini variant is recommended for apps sections that need quick selection access alongside content.

{{"demo": "pages/demos/drawers/MiniDrawer.js", "hideEditButton": true}}

## Responsive drawer

The `Hidden` responsive helper component allows showing different types of drawer depending on the screen width. A `temporary` drawer is shown for small screens while a `permanent` drawer is shown for wider screens.

{{"demo": "pages/demos/drawers/ResponsiveDrawer.js", "hideEditButton": true}}