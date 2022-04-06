## 使用JS修改CSS变量
### :root伪类
:root 这个 CSS 伪类匹配文档树的根元素。<br>
对于 HTML 来说，:root 表示 `<html>` 元素，除了优先级更高之外，与 html 选择器相同。<br>
在声明全局 CSS 变量时 :root 会很有用：
```
:root {
      --base: #ffc600;
      --sizing: 1;
      --spacing: 10px;
      --blur: 0px;
    }
```

### 移除事件
元素使用onEventName添加事件时,只需要`onEventName = null`就能移除事件执行

### CSS变量
声明变量的时候，变量名前面要加两根连词线（--）<br>
变量名大小写敏感<br>
var()函数用于读取变量。<br>
var()函数还可以使用第二个参数，表示变量的默认值。如果该变量不存在，就会使用这个默认值<br>
同一个 CSS 变量，可以在多个选择器内声明。读取的时候，优先级最高的声明生效。这与 CSS 的"层叠"（cascade）规则是一致的。
```
 <h2 style="--base: red;">Update CSS Variables with <span class='hl'>JS</span></h2>
 这里优先级比:root里高
```

#### JS操作CSS变量
getPropertyValue()获取样式值，只能获取到内联样式值<br>
setProperty()设置内联样式值
`document.documentElement.style.setProperty()`