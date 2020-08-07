# CSS布局

## 默认布局

`display` 的值为 `block`, `inline` 或者 `inline-block`。



## Flexbox

`display: flex`



## Grid

`display:grid`

## 浮动

[`float`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/float) 属性有四个可能的值：

- `left` — 将元素浮动到左侧。
- `right` — 将元素浮动到右侧。
- `none` — 默认值, 不浮动。
- `inherit` — 继承父元素的浮动属性。







## 定位

`position` 属性

- **静态定位(Static positioning)** `position: static;`
  是每个元素默认的属性——它表示“将元素放在文档布局流的默认位置——没有什么特殊的地方”。
- **相对定位(Relative positioning)** `position: relative;`
  允许我们相对于元素在正常的文档流中的位置移动它——包括将两个元素叠放在页面上。这对于微调和精准设计(design pinpointing)非常有用。
- **绝对定位(Absolute positioning)** `position: absolute;`
  将元素完全从页面的正常布局流(normal layout flow)中移出，类似将它单独放在一个图层中。我们可以将元素相对于页面的 `<html>` 元素边缘固定，或者相对于该元素的*最近被定位祖先元素(nearest positioned ancestor element)*。绝对定位在创建复杂布局效果时非常有用，例如通过标签显示和隐藏的内容面板或者通过按钮控制滑动到屏幕中的信息面板。
- **固定定位(Fixed positioning)** `position: fixed`
  与绝对定位非常类似，但是它是将一个元素相对浏览器视口固定，而不是相对另外一个元素。 这在创建类似在整个页面滚动过程中总是处于屏幕的某个位置的导航菜单时非常有用。
- **粘性定位(Sticky positioning)** `position: sticky;`
  是一种新的定位方式，它会让元素先保持和`position: static`一样的定位，当它的相对视口位置(offset from the viewport)达到某一个预设值时，他就会像`position: fixed`一样定位。



## 表格布局



## 多列布局