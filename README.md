# HTML,CSS基础复习

## 1. 什么是html文档与html元素

- html文档由各种类型的html元素组成,如文本, 图片等.
- 为了描述不同的信息类型, html元素必须要用不同的元素进行描述,例如文本元素,图像元素,链接元素等.
- html元素使用标签来描述, 不同的标签,具有不同的特征, 是通过它的属性进行描述.
- 如`<a href="">`, 元素叫:链接, 使用`<a>`标签描述, 它有一个`href=""`属性,指示跳转的地址
- html元素使用的标签根据元素类型, 可以分为双标签和单-标签二类
- 双标签,如`<li class="active">首页</li>`, 由起始标签与结束标签组成,内容写在这二个标签内部
- 双标签中, 属性必须写到起始标签中
- 单标签, 又叫空标签,或自闭合标签, 内容由标签中的某个属性设置,如`<img src="...">`
- 几乎所有的元素都可以添加`class, id, style`三个属性,用来查找与设置元素样式

------

## 2. html文档的结构是什么

- html文档是一个整体, 内部的所有元素都有自己的位置与功能, 存在于文档中的具体位置, 所有html文档是结构化的文档
- html文档中, 不允许也不可能存在存在一个完成自由的元素, 元素一定是某个元素的父级或同级, 或子级关系
- html文档的结构, 是一个倒置的"树型"结构, 基本文档结构如下:

```html
<!doctype html>
<!--html文档描述信息,供浏览器/搜索引擎分析-->
<head>
    <meta charset="utf-8">
    <title>defalut-title</title>
</head>
<!--html文档主体信息, 供浏览器窗口显示,供用户查看-->
<body>
<!--主体-->
</body>
```

------

## 3. html文档中的常用元素有哪些类型

- 所有元素是通过一个个矩形框来表示的
- 矩形框大体分为三类: 块元素, 行内元素, 行内块元素
- 块元素(`display: block`): 独占一行, 垂直排列, 可设置宽高
- 行内元素(`display: inline`): 共享一行, 水平排列, 不可设置宽高
- 行内块元素(`display: inline-bolck`): 共享一行,水平排列,但是可设置宽高

------

## 4. html中常用的块元素, 行内元素, 行内块元素有哪些

- **块元素**: 布局元素(`header,footer,main...`), 容器`div`, 标题段落`h1-h6,p`, 其它`table,ul,li,form...`
- **行内元素**: `span,strong,em...`, `a`, `input, label...`
- **行内块元素**: `img, iframe, video, audio...`

------

## 5. 什么是html文档中的不可替换元素和可替换元素

- 不可替换元素, 内容直接写在html文档中的元素标签内, 如`<p>php.cn</p>`, 通常用双标签表示
- 可替换元素, 通常是当前html文档引用的外部资源, 如图片, 视频, 文档等, 通常用单标签描述(也有例外)
- 如`<img src>`, `<video src="">`, `<link href="">`, `<script src=""></script>`都是可替换元素
- 因可替换元素只需要一个标签即可, 所以引用资源通过它的属性设置, 如`src`,属性值实际上外部资源在当前文档中的占位符
- 可替换元素是一个具体的外部资源, 除了脚本外, 大多是行内块元素方式显示在html文档中

------

## 6. html文档原始的布局方式是什么

- html文档中的元素, 默认是按书写顺序进行排列, 即先写的先显示, 从左到右, 从上到下, 自然排列
- 这种布局方式,叫自然流体布局, 或**文档流布局**, 也是最基本的布局方式
- 这种布局方式, 无法满足用户的个性化需求, 所以就诞生了CSS布局技术, 供用户编写个性化的页面

------

## 7. css是什么, 有什么用

- css是层叠样式表
- css用来控制html文档元素的:  **样式** 与 **布局**

------

## 8. css如何控制元素的样式

- 属性级: 通过元素添加`style`属性实现, 如 `<p style="color: red">php.cn</p>`, 仅适用当前元素
- 标签级: 通过给html文档添加`<style>`标签实现, 如`<style> p {color: red;} </style>`,仅适用当前文档
- 文档级: 创建独立的`css`文档, 在html文档中用标签`<link href="style.css">`引用, 适合所有引用它的文档,实现样式共享

------

## 9. css的基本语法是什么

- 样式规则 = 选择器 + 样式声明
- 选择器: 用来查找页面满足条件的元素
- 样式声明: 由 "属性"和"值"二部分组成,中间用冒号分隔, 用分号结束,如`color:red;`
- 行内级: `<p style="color:red; font-size: 2rem">php.cn</p>`
- 文档级: `<style> p {color: red; font-size: 2rem} </style>`

------

## 10. css常用的简单选择器有哪些

- 标签选择器: `div {width: 100px; height: 100px; border: 1px solid;}`
- 属性选择器: `input[type="text"]`
- 类选择器: `.active {color: yellow}`, 获取具有`class`属性元素的快捷方式
- id选择器: `#app {background: #ccc}`, 获取具有`id`属性元素的快捷方式
- 群级选择器: `div, p, ul, h3 {margin: 0;}`
- 后代选择器: `div p {...}`
- 子元素选择器: `div > p {...}`
- 相邻同级选择器: `div + p {...}`（选择紧接在 <div> 元素之后的所有 <p> 元素。）
- 相邻所有级选择器: `div ~ p {...}`（选择前面有 <div> 元素的每个 <p> 元素。并且选中的p还需要和div同级）
- 通配符选择器: `main * {padding: 0}`（选中main下的所有元素）

------

## 11. css选择器的优先级是什么

- 常规状态下: id > class > tag(标签)

------

## 12. 伪类选择器

- 伪类选择器,本质上仍是类选择器, 级别高于标签选择器, 这点必须要当心
- 所谓"伪"类, 就是不需要给元素添加类class属性, 也可获取到页面元素, 如何做到的呢, 看下面
- 伪类元素有许多应用场景, 可以根据元素的位置, 状态等信息来获取元素
- `:hover`, `:active`, `:ennable`, `:require`..., 等
- 我们重点放在它的最重要的应用场景上: 根据元素位置来获取元素

------

## 13. `:nth-child(n)`

- 根据子元素索引位置来获取元素
- 参数n: 可以使用字面量正整数和表达式
  - 字面量正整数: 直接定位子元素, 默认从1开始
  - 表达式: n 默认从0开始

```html
<ul>
    <li>item1</li>
    <li>item2</li>
    <li>item3</li>
    <li>item4</li>
    <li>item5</li>
</ul>
```

```css
/* 1. 正整数字面量参数, 必须使用正整数,不允许是负数*/

/* 匹配第一个子元素: <li>item1</li> */
ul > :nth-child(1) {...}

/* 匹配第三个子元素: <li>item3</li> */
ul > :nth-child(3) {...}

/* 匹配最后一个子元素: <li>item3</li> */
ul > :nth-child(5) {...}

/* 第一个和最后一个有快捷方式 */
/* :first-child, :last-child */
ul > :first-child {...}
ul > :last-child {...}

/* 还可逆序,倒数查询 */
/* 例如第二个 */
ul > :nth-last-child(2) {...}

/****************************************/

/* 2. 表达式 , 注意n从0开始*/

/* 匹配前2个 */
ul > :nth-child(-n+2) {...}

/* 从第3个开始 */
ul > :nth-child(3+n) {...}

/* 匹配最后二个 */
ul > :nth-last-child(-n+2) {...}
```

------

## 14. `:nth-of-type(n)`

- 根据子元素在**分组中**的索引位置来获取元素
- 这组选择器与`:nth-child(n)`极其相似,一定要注意区分
- `nth-of-type(n)`, 比上面一个多一个步骤: 分组
- 对一组元素分组,必须要有一个分组/分类的依赖, 是根据元素类型, 即标签名称
- 参数n的规则与`:nth-child(n)`是一样的
- 参数n: 可以使用字面量正整数和表达式
  - 字面量正整数: 直接定位子元素, 默认从1开始
  - 表达式: n 默认从0开始

```html
<ul>
    <li>item1</li>
    <p>第1个p元素<p>
    <li>item2</li>
    <li>item3</li>
    <p>第2个p元素<p>
    <p>第3个p元素<p>
    <li>item4</li>
    <p>第4个p元素<p>
    <li>item5</li>
</ul>
```

```css
/* 1. 正整数字面量参数, 必须使用正整数,不允许是负数*/

/* 匹配子元素p中的第一个: <p>第1个p元素<p> */
ul > p:nth-of-type(1) {...}

/* 匹配子元素p中的第3个: <p>第3个p元素<p> */
ul > p:nth-of-type(3) {...}

/* 第一个和最后一个有快捷方式 */
/* :first-of-type, :last-of-type */
ul > p:first-of-type {...}
ul > p:last-of-type {...}

/* 还可逆序,倒数查询 */
/* 例如第二个 */
ul > p:nth-last-of-type(2) {...}

/****************************************/

/* 2. 表达式 , 注意n从0开始*/

/* 匹配前2个 */
ul > p:nth-of-type(-n+2) {...}

/* 从第3个开始 */
ul > p:nth-of-type(3+n) {...}

/* 匹配最后二个 */
ul > p:nth-last-of-type(-n+2) {...}
```

------

## 15. 什么是盒模型五要素

- `width`: 宽度
- `height`: 高度
- `padding`: 内边距
- `border`: 边框
- `margin`: 外边距
- 元素值的简写口诀: 第二个值,始终代表: "左右"

------

## 16. 影响盒子大小的因素是什么,如何避免

- `padding`, `border` 默认值为`0`, 所以,正常状态下, 盒子大小由`width | height`确定

```css
/* 用户期望的盒子内容大小是: 宽200px, 高150px */
.box {
    width: 200px;
    height: 150px;
}

/* 添加内边距padding后, 盒大小更新为: 220px, 170px */
.box {
    padding: 10px;
}

/* 添加border边框后, 盒大小再次更新为: 230px, 180px */
.box {
    border: 5px solid;
}
/*
此时,如果页面上仍有其它元素, 势必会受到这个盒子尺寸变大的影响,如果避免这种情况发生呢?
可以通过重置盒子的width/height来实现, 即缩放原盒子尺寸
*/

/* 将width/height大小限制到边框级, 使盒大小重新回到200px, 150px */
.box {
    box-sizing: border-box;
}
/* 当然也可以将大小限制到content级: content-box */
```

------

## 17. 影响盒子在包含块中的位置的因素是什么

- 影响元素在父级区块中的位置的属性是: `margin`
- `margin`值会影响到元素之间的间隙,在水平和垂直方向上的表现不同,垂直方向上不会累加,而是折叠
- `margin: auto`: 支持`auto`, `auto`会触发浏览器的自动计算功能, 会将剩余空间尽可能多的分配给当前元素
- 格式化块元素: 指设置了/限制了`width / height`属性的元素
- 格式化上下文: 是指当前元素存在于一个受限的空间内, 它的父级有自己的宽/高,而不是由子元素自动撑开
- `auto`可以轻松实现块元素在水平方向上的: 居左, 居中, 居中分布
- `margin-left: auto`, `margin-right: auto`, `margin:auto`
- 提示: `text-align: left | center | right`, 实现行内元素在水平方向上的居左, 居中, 居中分布

------

## 18. 浮动的本质是什么, 使用中要注意什么

- `float`: 本质是实现图文混排, 并非用于而已
- 使用`float`布局是一种`Hack`用法, 是借用而已
- `float`: 会破坏文档流布局, 注意并不是由元素脱离文档,只影响到后面元素排列
- 文档流: 也叫自然流,元素的排列顺序与书写顺序一致, 从左到右,从上到下
- 浮动是魔鬼, 布局时尽可能避免使用, 而是使用下面要学习的`flex`或`grid`
- 块级元素的对齐/居中, 如导航, 比较margin和float区别
- 子元素浮动会使它的让包含块(父元素)高度塌陷/折叠
- 子元素浮动会使父元素高度消失,产生折叠,破坏了整体布局
- 解决方案有许多, 如添加伪元素, 添加附加元素清浮动
- `clear: left | right | both`: 清除浮动
- 最简单就是: `overflow: hidden/auto`, `BFC`块级格式化上下文

## 20. 如何通俗的理解元素定位`position`的各种形式

- 元素定位,应该是最直观的布局方式了
- 静态布局`position: static`: 元素默认是按文档流方式,就是书写顺序排列
- 跟它类似的是"相对定位", 元素相对它原来的位置发生偏移,`positon: relative`
- 相对定位,类似于"停薪留职", 我只是临时离开一下, 我的岗位还在呢, 不能被人顶替了
- 还有一种是绝对定位,类似于"下岗/失业", 彻底与原-单-位脱离,成为自由人, 到哪个单-位上班, 就属于哪个单-位
- 也就是说, 绝对定位元素, 必须要指定它的工作单-位, 就是它相对于谁定位, 如果不指定,那它就是自由人,属于社会
- 在html文档中, 最高层级的元素就是根元素html, 它就是社会, 这个时候, 绝对定位元素是相对于html定位的
- 所谓"固定定位", 最好理解, 元素就是一个社会自由人, 总是相对于html,这个根元素定位,除了html,哪个也管不了它

## 17. 绝对定位的典型应用

- 拥有定位属性的元素叫: 定位元素
- 块级元素的水平居中,非常容易实现, 但是垂直居中一直是前端开发者心中永远的痛
- 之前的传统方式, 用百分比拉来拉去, 我就不提了,几乎很少用了,大家感兴趣, 问一下度度
- 我来介绍一下,使用定位元素快速实现的解决方案:（这种方式是需要设置子元素的宽和高的）

```html
<div class="parent">
    <div class="sub"></div>
</div>
```

```css
.parent {
    width: 300px;
    height: 200px;
    background-color: yellow;
    /* 定位父级/包含块 */
    position: relative;
}

.sub {
    width: 200px;
    height: 100px;
    background-color: lightblue;

    /* 此时子元素转为定位元素,并且是相对于父级块的全部空间区域
    而子元素又是有width/heigt限制的格式化元素
    这样, 父级与子级之间的空间就全部被空出来了,可以供margin: auto计算了 */
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    /* 水平垂直居中 */
    margin: auto;
}

```
