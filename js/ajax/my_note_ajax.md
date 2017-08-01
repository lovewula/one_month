ajax 不通过form单单post传输需要添加

```
xhr.setRequestHeader('content-type' , 'application/x-www-form-urlencoded');
```
form表单默认支持