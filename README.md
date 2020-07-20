# pixel-border

解决移动端1px边框的通用CSS工具。

# 安装

npm安装：
```
npm install pixel-border --save
```

yarn安装：
```
yarn add pixel-border
```

浏览器安装，建议安装压缩后的版本：
```html
<link rel="stylesheet" href="path/to/pixel-border.min.css"><link>
```

# 使用

pixel-border 通过元素的 ::before 伪元素使用 transform 缩放为元素设置边框。因此，你可以使用原生的 CSS 边框属性为原素设置边框，只需要在元素上添加一个 pixel-border 或 pixel-border="true" 的属性，并设置元素的 border-style 值即可。如下会创建一个单像素边框：
```html
<div pixel-border style="border-style: solid;">单像素边框</div>
```

> **注意：**pixel-border已为元素的边框设置为固定值 1px，因此不要为元素再设置 border-width，并且元素的 box-sizing 值被设置为 border-box，请不要重置为其他类型的值。

**设置任意边框：**

设置元素某一边的边框时，只需为元素设置 border-top-style、border-bottom-style、border-left-style、border-right-style 其中一项的值，并设置元素 border-color 的值即可。如下设置上边边框：
```html
<style>
  .border-top {
    border-top-style: solid;
    border-top-color: red;
  }
</style>

<div class="border-top" pixel-border>上边框</div>
```

**设置圆角边框：**

当需要圆角边框时，始终为 border-radius 设置百分比值。如下：
```html
<style>
  .border-radius {
    width: 100px;
    height: 100px;
    border-style: solid;
    border-color: red;
    border-radius: 10%;
  }
</style>

<div class="border-radius" pixel-border>圆角边框</div>
```