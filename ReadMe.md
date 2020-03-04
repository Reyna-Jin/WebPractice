README
===============
在线直播课程实战[千千音乐](http://music.taihe.com/)网页制作
【注：此为针对PC端的网页制作（非响应式）】

***
# HTML5

## 标签

### 常用标签-布局标签

|标签|效果|
|---|-----|
|`<h1/>-<h6>`|6个等级的网页标题|
|`<p></p>`|定义段落|
|`<div>`、`<span>`|盒子|
|`<header></header>`|页面内容的头部|
|`<nav></nav>`|导航标签|
|`<section></section>`|定义文档某个区域|
|`<footer></footer>`|尾部标签|
|`<ul> <li></li> </ul>`|无序列表标签|
|`<ol> <li></li> </ol>`|有序列表标签|


* `<section>`类似大的`<div>`

* `<nav>`导航栏常用
* `<ul><li></li></ul>`排列整齐;页面布局即可实现并列排放
导航栏nav包含`<ul>` `<li>`

![li.png](li.png)

* footer举例
![footer.png](footer.png)

---

### 常用标签-链接标签
#### 链接语法格式
* `<a href="跳转目标" target="目标窗口的弹出方式"> 文本或图像 </a>`
	* `<a href ="#">空链接</a>`
	* `target="_blank"`在新标签页打开
#### 图像标签
* `<img src="图像URL" alt="图片显示不出时出现文字信息">`

>快捷键
>> w200   |  width：200px

---

## 路径
相对路径分类|分类|说明
---|---|----
同一级路径| |\<img src="baidu.gif">
下一级路径|/|\<img src="images/baidu.gif">
上一级路径|../|\<img src="../baidu.gif">

---

# CSS3
层叠样式表
## 标签选择器
为页面中某一类标签指定统一的CSS样式

![css.png](css.png)
```html
<style>
	/*style标签里面写样式*/
	/*选择器 { 属性: 值；}*/
	/*选择哪个标签 { 改什么样式}*/
	div {
		width: 200px;
		height: 200px;
		background-color: pink;
	}
</style>
```
## 类选择器
差异化选择不同的标签
```html
<html>
<head>
	<style>
		.red {
			color:red;
		}
	</style>
</head>
<body>
	<div class="red font25">hello</div>
</body>
</html>
```
>在开发中，三个并列的矩形但显示颜色不同，即为类选择器的作用
>口诀：样式点定义，结构类调用，一个或多个，工作最常用

## id选择器
为标有特定id的HTML元素指定特定的样式
```html
<html>
<head>
	<style>
		#pink {
			color:deeppink;
		}
	</style>
</head>
<body>
	<div id="pink">hello</div>
</body>
</html>
```
>口诀：样式#定义，结构id调用，只能调用一次，别人勿调用

## 后代选择器
	ul li { 样式声明 }	/* 选择ul里面所有的li标签元素 */
>输入快捷方式：ul>li*3{我是ul的儿子}

## 并集选择器
选择多组标签，同时为他们定义相同的样式

	ul,div { 样式声明 }	/* 选择ul和div标签元素 */

## 盒子模型组成
css用div来布局
* 盒子边框
```html
<style>
        div {
            width: 100px;
            height: 100px;
            background-color: pink;
            /* solid 实线边框   dotted 点线边框   dashed 虚线边框 */
            border: 1px green solid;
        }
    </style>
```

* 内边距 padding
```html
    <style>
        div {
            border: 1px rgb(8, 74, 8) solid;
            padding-left: 25px;
            padding-top: 20px;
            padding: 10px;
        }
    </style>
```

* 外边距 margin
```html
    <style>

        div {
            padding: 10px 30px;
            margin: 20px;
        }
    </style>
```

* 不撑大盒子  box-sizing: border-box;

	使用border和padding时都会把盒子撑大——css默认的盒子模型`box-sizing: content-box;`
	css3盒子模型-padding和border不会撑大盒子 `box-sizing: border-box;`

>margin: 0 auto;	//块居中

---
## CSS3圆角边框
`border-radius: length;`
* 参数值可为数值或百分比
* 正方形->⚪
	* 数值为高度的一半
	* 50%
* 长方形->椭圆
	* 短边的一半

## CSS3盒子影子
`box-shadow: h-shadow v-shadow blur spread color inset`
![shadow.png](0)
* rgba(0,0,0, .3);最后的.3是透明度
* 盒子阴影不占空间，不会影响其他盒子排列
>tips:
>>模拟鼠标经过，F12选中选择左上的小箭头选中“情感”右键focus :hover 可看到box-shadow设置的值大小

## 2D转换 transform
* 移动：translate
* 旋转：rotate
* 缩放：scale
```html
div:hover {
            transform: translate(0, 30px);
            transform: rotate(30deg);
            transform: scale(2,2);
        }
```

## 过渡动画 transition
`transtion: 过渡的属性 花费时间 运动曲线(ease)
 何时开始(1s)`
* 谁做动画给谁加，div动，写在div中，而不是div:hover中

## 元素显示模式 display
![display](display.png)
* 转换为块元素：display:block;
* 转换为行元素：display:inline;
* 转换为行内块：display:inline-block;

## 浮动 float
### 标准流
标签按照规定好默认方式排列

### 浮动
浮动元素会脱离标准流，不保留位置
让多个块级盒子一行没有缝隙排列显示，横向排列盒子

	选择器 { float: 属性值; }
|属性值|描述|
|---|---
none|元素不浮动
left|元素向左浮动
right|元素向右浮动

### 定位
让盒子自由的在某个盒子内移动位置或固定屏幕中某个位置，并压住其他盒子

	定位=定位模式+边偏移

* position

![position](position.png)

* 边偏移

![pianyi](pianyi.png)
布局使用

**子绝父相**

## 字体图标
通过F12可以改变网页中字体图标的颜色

* icomoon字库 http://icomoon.io

* 阿里iconfont字库 http://www.iconfont.cn/

* 批量下载
```javascript
var span = document.querySelectorAll('.icon-cover');
for(var i = 0, len = span.length; i < len; i++){
	console.log(span[i].querySelector('span').click());
}
```

* 字体图标的使用
```html
<!DOCTYPE html>
<head>
    <!-- 1. html先引用字体库里面的css 文件 iconfont.css -->
    <link rel="stylesheet" href="fonts/iconfont.css">
    <style>
        span {
            font-size: 60px!important;
            color: pink;
        }
    </style>
</head>
<body>
   <!-- 2. 给元素添加类名即可--->
   <span class="iconfont icon-dollar"></span>
   <span class="iconfont icon-gift"></span>
</body>
</html>
```

---
# CSS属性书写顺序
```html
div {
            /* 1. 布局浮动定位 显示隐藏 */
            position: absolute;
            float: left;
            /* 2. 盒子模型相关   */
            width: 100px;
            height: 100px;
            background-color: #fff;
            /* 3. 文字字体类 */
            font-size: 12px;
            color: pink;
            /* 4. css3 特殊样式  圆角 等等*/
        }
```

只有定位才用到top，right
github、gitee（码云）查找项目实战
黑马程序员官网看
