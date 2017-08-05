Ajax 简单的说就是不重新加载整个网页的情况下，Ajax通过后台加载数据，并在网页上显示，原生js写Ajax特别麻烦，而且涉及到兼容性问题，但是使用jQuery可以轻松实现，而不用关心底部具体的细节，以下将对Ajax的几种方法进行详解：

1. `$.get(url, [params])`方法：向`url`这个地址发送一个`get`请求，数据可以放在`params`这个参数中
2. `$.post(url, [params])`方法：向`url`这个地址发送一个`post`请求，数据可以放在`params`这个参数中
3. `$.ajax(url, [params])`方法：以上两个方法的底层实现
