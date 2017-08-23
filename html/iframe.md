### `iframe`

内联框架用于在网页中显示网页。iframe标签可以很方便地创建框架，但由于创建一个框架意味着要创建一个完整的页面环境，很耗费资源；因此能不用就尽量不用

【属性】

* src 规定在内联框架中显示的文档的URL

* name 规定内联框架的名称，用于在javascript中引用元素或作为链接的目标

* height 规定iframe的高度

* width 规定iframe的宽度

* longdesc 指向带有内联框架内容长描述的页面(已废弃)

* frameborder(已废弃)

  * ```css
    frameborder="0"//无边框
    frameborder="1"//(默认，有边框)    
    ```

* scrolling(已废弃)

  * ```css
    scrolling="auto"//默认，需要时显示滚动条
    scrolling="yes"//始终显示滚动条
    scrolling="no"//从不显示滚动条
    ```

* seamless 规定iframe看上去像是包含文档的一部分，设置该属性后，iframe无边框或滚动

* sandbox 启用对`<iframe>`中内容的限制，可以用空格分隔多个属性值(IE9-不支持)

  * ```css
    sandbox=""//应用所有的限制
    sandbox="allow-same-origin"//允许iframe内容被视为与包含文档有相同的来源
    sandbox="allow-top-navigation"//允许iframe内容从包含文档导航加载内容
    sandbox="allow-forms"//允许表单提交
    sandbox="allow-scripts"//允许脚本执行
    ```

* srcdoc 规定在iframe中显示的页面的HTML内容(IE浏览器不支持)，若浏览器支持srcdoc属性，则将显示srcdoc属性的内容；否则将显示src属性中规定的文件

  * ```css
    <iframe srcdoc="<p>Hello world!</p>" src="/demo/demo_iframe_srcdoc.html">
    </iframe>
    ```

  ​