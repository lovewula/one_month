## Ajax post

如果`ajax`请求的`method`方法为`post`就要加上下面这段话

```javascript
xhr.setRequestHeader('content-type' , 'application/x-www-form-urlencoded');
```

