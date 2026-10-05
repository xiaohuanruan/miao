# 快速入门

欢迎来到 React 文档! 本章节将介绍你每天都会使用的 80% 的 React 概念.


**你将会学习到**
```
* 如何创建和嵌套组件
* 如何添加标签和样式
* 如何显示数据
* 如何渲染条件和列表
* 如何对事件做出响应并更新界面
* 如何在组件间共享数据
```
## 创建和嵌套组件
React 应用程序是由 **组件** 组成的. 一个组件是由 UI (用户界面) 的一部分, 它拥有自己的逻辑和外观.组件可以小到一个按钮,也可以大到整个页面.

React 组件是返回标签的 JavaScript 函数:

```
function MyButton() {
	return (
	<button>我是一个按钮</button>
	);
}
```
至此,你已经声明了 ```MyButton```,现在把它嵌套到另一个组件中:
```
export default function MyApp() {
	return (
	<div>
		<h1>欢迎来到我的应用</h1>
		<MyButton />
	</div>	
	);
}
```
你可能已经注意到```<Mybutton />```是以大写字母开头的.你可以据此识别 React 组件. React 组件必须以大写字母开头,而 HTML 标签则必须是小写字母.
来看下效果:
```
function MyButton() {
  return (
    <button>
      我是一个按钮
    </button>
  );
}

export default function MyApp() {
  return (
    <div>
      <h1>欢迎来到我的应用</h1>
      <MyButton />
    </div>
  );
}
```

![image-20260930143831227](C:\Users\a1819\AppData\Roaming\Typora\typora-user-images\image-20260930143831227.png)
```export default```关键字指定了文件中的主要组件.如果你对 JavaScript 某些语法不熟悉,可以参考[MDN](https://developer.mozilla.org/zh-CN/docs/web/javascript/reference/statements/export)和[javascript.info](https://zh.javascript.info/import-export).
## 使用JSX编写标签
上面所使用的标签语法被称为**JSX**.它是可选的,但大多数React项目会使用JSX,主要是它很方便.所有[我们推荐的本地开发工具](https://zh-hans.react.dev/learn/installation)都开箱即用地支持JSX.
JSX比HTML更加严格.你必须闭合标签,如```<br />```.你的组件也不能返回多个JSX标签.你必须将它们包裹到一个共享父级中,比如```<div>...</div>```或使用空的```<>...</>```包裹:
```
function AboutPage() {
  return (
    <>
      <h1>关于</h1>
      <p>你好。<br />最近怎么样？</p>
    </>
  );
}
```
如果你有大量的HTML需要转移到JSX中,你可以使用[在线转换器](https://transform.tools/html-to-jsx).
## 添加样式
在React中,你可以使用```className```来指定一个CSS的class.它与HTML的[class](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Global_attributes/class)属性的工作方式相同:
```
<img className="avatar" />
```
然后,你可以在一个单独的CSS文件中为它编写CSS规则:
```
/* 在你的 CSS 文件中修改 */
.avatar {
  border-radius: 50%;
}
```
React并没有规定你如何添加CSS文件.最简单的方式是使用HTML的```<link>```标签.如果你使用了构建工具或框架,请阅读其文档来了解如何将CSS文件添加到你的项目中.
