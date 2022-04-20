## fetch
> Fetch API 能够执行XMLHttpRequest对象的所有任务，但更容易使用，接口也更现代化，能够在Web工作线程等现代Web工具中使用。XMLHttpRequest 可以选择异步，而 Fetch API 则必须是异步。


fetch与XMLHttpRequest相比，在使用上方便了很多
```js
fetch('bar.txt')
.then((response) => response.text())
.then((data) => console.log(data));
```
fetch一些不完美
* fetch只对网络请求报错，对400，500都当做成功的请求，需要封装去处理
* fetch默认不会带cookie，需要添加配置项 fetch(url, {credentials: ‘include’})
* fetch不支持abort，不支持超时控制，使用setTimeout及Promise.reject的实现的超时控制并不能阻止请求过程继续在后台运行，造成了流量的浪费
* fetch没有办法原生监测请求的进度，而XHR可以

总结：一般的请求可以用fetch解决，复杂的需要借用第三方库

## replace
replace方法对于替换字符是个高效的方法
`str.replace(regexp|substr, newSubStr|function)`
第一个参数可以是字符串或者正则
第二个参数是替换的字符和一个函数
当是字符串时，还可以插入一些特殊字符 [mdn](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/replace#%E4%BD%BF%E7%94%A8%E5%AD%97%E7%AC%A6%E4%B8%B2%E4%BD%9C%E4%B8%BA%E5%8F%82%E6%95%B0)
##### 交换字符串中的两个单词
```js
const re= /(\w+)\s(\w+)/;
const str = "John Smith";
const newStr = str.replace(re, "$2, $1");
// Smith, John
console.log(newStr);
```
