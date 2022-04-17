## 可伸缩的图片墙
页面上有两个动画效果，文字出现和panel宽度<br>
要点：如何触发事件后，再触发就取消，类似JQuery，toggle的效果<br>

既然是动画那么就通过CSS类进行绑定，事件没有toggle，但是元素对象classList有个方法toggle，对类进行移除和添加。
> bug: 使用transitionend事件监听，当panel展开时，显示上下两行字，如果在点击panel时，还没有展开马上又点，toggleOpen执行了两次，toggleActive只执行了一次
> 解决：需要在设置toggleOpen时候记录当前是展开还是折叠，然后在toggleActive时与active类样式是否存在进行与或判断

flex: flex-grow flex-shrink flex-basis;<br>
1. flex-grow: 设置flex项主尺寸的flex 增长系数。
2. flex-shrink：定了flex元素的收缩规则。flex 元素仅在默认宽度之和大于容器的时候才会发生收缩，其收缩的大小是依据flex-shrink的值。
3. flex-basis: 指定了 flex 元素在主轴方向上的初始大小


