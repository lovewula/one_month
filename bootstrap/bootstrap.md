# Bootstrap

## `Bootstrap`是什么

`bootstrap`是一个最受欢迎的 HTML、CSS 和 JS 框架，用于开发响应式布局、移动设备优先的 WEB 项目。通俗的讲，`bootstrap`就是预先定义好了一套优美的`CSS`样式和一套`组件`，前端开发者可以直接拿来使用，加速开发效率，并且他是响应式布局的，所以写的一套代码可以在多种设备中进行使用。

## ` Bootstrap`怎么用

要使用`bootstrap`很简单，只要[下载](https://github.com/twbs/bootstrap "")源代码，然后把`bootstrap.min.css`和`bootstrap.min.js`以及`jquery.min.js`导入到`html`文件中即可使用。或者是使用[bootcss](http://www.bootcss.com/ "")网站提供的`CDN`加速服务，把链接导入到`HTML`文件中即可，要注意的事情是，`jquery`必须放在`bootstrap.min.js`之前，因为`bootstrap.min.js`依赖`jquery`，那么以下将使用`CDN`的方式展示样例代码：

```html
<!-- 新 Bootstrap 核心 CSS 文件 -->
<link rel="stylesheet" href="http://cdn.bootcss.com/bootstrap/3.3.0/css/bootstrap.min.css">
<!-- jQuery文件。务必在bootstrap.min.js 之前引入 -->
<script src="http://cdn.bootcss.com/jquery/1.11.1/jquery.min.js"></script>
<!-- 最新的 Bootstrap 核心 JavaScript 文件 -->
<script src="http://cdn.bootcss.com/bootstrap/3.3.0/js/bootstrap.min.js"></script>
```
## `bootstrap`中的栅格系统：

`bootstrap`中最强大也是最核心的一个东西就是响应式，而响应式是通过一个叫做**栅格系统**的东西实现的。栅格系统把一个页面分成12列，`bootstrap`会根据媒体查询获取当前的浏览器的宽度，然后再把宽度平均分配给12列，`html`中一个盒子可以占用多列。要使用栅格系统，需要使用到`container/container-fluid`和`row`以及`col-xs-/col-sm-/col-md-/col-lg-`类。`container`相当于一个`table`盒子，装着许许多多的`row`，每个`row`里面装着许许多多的`col`，通过这样一种结构，构成了一个栅格系统，而`container`和`container-fluid`的唯一区别是，`container-fluid`是全屏的，而`container`不是全屏的，左右两边会有一个间距。