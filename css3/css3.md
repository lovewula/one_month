## `border-radius`

```
border-top-left-radius: 200px 100px;  /* x  y*/
border-top-right-radius: 200px 100px;  /* x  y*/
border-bottom-right-radius: 200px 100px;  /* x  y*/
border-bottom-left-radius: 200px 100px;  /* x  y*/
```

```
//完整的圆:
div{
background:red;
height:200px;
width:200px;
margin:50px auto;
border-radius:50%;//圆的四角都百分之50% 或者写200px也可以
}
//半圆:
div{
background:red;
height:200px;
width:100px;
margin:50px auto;
border-top-left-radius: 100px;//左上角圆边角100px 根据宽度设置
border-bottom-left-radius: 100px;//左下角圆边角100px 同上
}
//四边角都可以单独设置圆边角
border-top-left-radius:值;//左上角
border-top-right-radius:值;//右上角
border-bottom-left-radius:值;//左下角
border-bottom-right-radius:值;//右下角
//border-上或下-左或右-radius:值;
```



## 阴影

`CSS3`提供了2种阴影一种是文字阴影，一种是像框内添加阴影文字阴影:`text-shadow`:水平 垂直 模糊半径 阴影度 阴影颜色 向内或向外;6个参数 水平与垂直是必须项，其他随意向内或向外默认情况下是向外阴影的元素式的阴影:`box-shadow`:值与文字阴影相同

```

box-shadow:5px 5px 10px black;//水平与垂直值可以为负数
text-shadow:5px 5px 10px black;
//向内阴影只需要在最后面添加inset即可，默认为向外阴影(outset)
box-shadow:5px 5px 10px black inset;
```

