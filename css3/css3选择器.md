# CSS3

## CSS3增加了三大类选择器

* 属性选择器
* 结构伪类选择器
* UI元素状态伪类选择器



### 属性选择器

**通过属性来选择元素**



| 属性选择器(`E`指元素`element`,`attr`指属性名`attribute`) |             说明(Description)              |
| :--------------------------------------: | :--------------------------------------: |
|            `E[attr$="wula"]`             | 选取元素`E`,如果元素中有`attr`属性而且属性是以`wula`结尾的，就会被选中该元素 |
|            `E[attr^="wula"]`             | 选取元素`E`,如果元素中有`attr`属性而且属性是以`wula`开头的，就会被选中该元素 |
|            `E[attr*="wula"]`             | 选取元素`E`,如果元素中有`attr`属性而且属性任何位置包含了`wula`就会被选中该元素 |

**示例在**[`CSS3`属性选择器](file:///D:/%E5%A4%87%E8%AF%BE/one_month/css3/css3%E5%B1%9E%E6%80%A7%E9%80%89%E6%8B%A9%E5%99%A8.html)

## 结构伪类选择器

**针对`HTML`层次_结构_的伪类选择器**



| 选择器(selector)     | 说明(Description)                          |
| ----------------- | ---------------------------------------- |
| `E:nth-child(n)`  | 选择父元素下的第`n`个子元素或者奇偶,`odd(奇数) | even(偶数)` |
| `E:first-child`   | 选择父元素的第一个子元素                             |
| `E:last-child`    | 选择父元素的最后一个子元素                            |
| `E:only-child`    | 选择父元素中唯一的子元素（该父元素只有一个子元素）这样可以用派生选择器      |
| **示例 **           | [`css3`伪类选择器之`child`](file:///D:/%E5%A4%87%E8%AF%BE/one_month/css3/css3%E4%BC%AA%E7%B1%BB%E9%80%89%E6%8B%A9%E5%99%A8%E4%B9%8Bchild.html)· |
| `E:nth-of-type`   | 选择同类型的第`n`个兄弟元素，也是能传`odd`和`even`         |
| `E:first-of-type` | 选择同类型的第一个同级兄弟元素                          |
| `E:last-of-type`  | 选择同类型的最后一个同级兄弟元素                         |
| `E:only-of-type`  | 选择父元素中特定类型的唯一子元素（该父元素有多个子元素）             |
| **示例**            | [`css3`伪类选择器之`type`](file:///D:/%E5%A4%87%E8%AF%BE/one_month/css3/css3%E4%BC%AA%E7%B1%BB%E9%80%89%E6%8B%A9%E5%99%A8%E4%B9%8Btype.html) |
| `:root`           | 选择文档的根元素 ，在 `HTML`中，根元素永远是`HTML`         |
| `E:not(selector)` | 选择某个元素之外的所有元素                            |
| `E:empty`         | 选择一个不包含任何子元素的元素，注意文本节点也可以看成子元素           |
| `E:target`        | 选取页面中的某个`target`元素,`target`就是该元素被当作页面超链接类使用，描点 |
| **示例**            | [css3伪类选择器之others](file:///D:/%E5%A4%87%E8%AF%BE/one_month/css3/css3%E4%BC%AA%E7%B1%BB%E9%80%89%E6%8B%A9%E5%99%A8%E4%B9%8Bothers.html) |



## Ul元素状态伪类选择器

说的很专业是吧，其实就是啥，就是`UI`元素的伪类选择器，`ul即(User Interface)`，一般情况下，`uI`元素状态包括：

* 可用 (`enabled`)

* 不可用(`disabled`)

* 选中 (`checked`)

* 没选中(``)

* 获取焦点 (`focus`)

* 失去焦点

* 等等

  这些选择器的**共同特征**是：指定的样式只有当元素处于某种状态下才起作用，在默认状态下不起作用，UI元素状态伪类选择器大多数都是针对表单元素来使用的

  | 选择器（selector）  | 说明（Desscription） |
  | -------------- | ---------------- |
  | `E:enabled`    | 选取`E`中所有的可用元素    |
  | `E:disabled`   | 选取`E`中所有的不可用元素   |
  | `E：focus`      | 获得焦点的时候使用激活      |
  | `E:checked`    | 被选中的元素           |
  | `E:selection`  | 改变被选择的网页文本显示效果   |
  | `E:read-write` | 可读写的元素           |
  | `E:read-only`  | 只读的元素            |
  | `E:after`      | 之后插入内容           |
  | `E:after`      | 之前插入内容           |
  |                |                  |


  