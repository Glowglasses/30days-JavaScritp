## 实现按下ASDFGHJKL键后有乐器的声音与CSS动画

### transitionend事件
transitionend 事件在 CSS 完成过渡后触发。<br>
如果过渡在完成前移除，例如 CSS transition-property 属性被移除，过渡事件将不被触发。<br>
所以在一直按着键后就会导致样式无法移除的bug。（本来该移除样式，还没进行完就又加上了）<br>
需要判断是否进入transitionend事件中，然后在键松开时进行手动移除样式

### HTMLCollection
通过getElementsByClassName获取到的值的类型不是数组而是一个类数组<br>
需要通过`for of | Array.from().forEach()` 来遍历