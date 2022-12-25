# css引入

层叠样式表（cascading style sheets)

```html
<head>
<title></title>
    <style>
		p{
            color:red;
		}
    </style>
</head>
```

1. 内嵌式：css写在style标签中

2. 外联式：css写在一个单独的.css文件中

   - 通过link标签在网页中引用

     ```html
     <link rel="stylesheet" href="css文件路径">
     ```

     

3. 行内式：css写在标签的style属性中

# 基础选择器

## 1.标签选择器

```html
选择器{
	属性名：属性值；
}
#选中所有的这个标签都生效css
```

## 2.类选择器

`.类名{css属性名“：属性值；}`

所有标签上都有class属性，class属性的属性值叫类名

一个标签可以使用多个类名，类名间用空格隔开即可

## 3.id选择器

`#id属性值{css属性名：属性值；}`

所有标签都有id属性

一个标签只能有一个id属性值

一个id选择器只能选中一个标签

## 4.通配符选择器

`*{css属性名：属性值；}`

==众生平等符==

# 字体和文本样式

## 字体

### 字体大小

`默认字号16px`

```html
<style>
		p{
			font-size: 30px;	#px必须有
		}
</style>
```

### 字体粗细

`font-weight:100~900；`

### 倾斜

`font-style:italic;`倾斜

`font-style:nomal;`正常

### 字体

默认字体：微软雅黑

`font-family:字体名称1 字体2 字体3`

### 样式的层叠问题

```html
<style>
	p{
		color: red;
		color: blue;
	}
</style>
#p的内容为蓝色
```

### 字体font相关属性的连写

`font:style weight size family;`==顺序不能变==

只能省略前两个，相当于默认值

## 文本

### 文本缩进

`text-indent：；`

em：一个字的大小

text-indent：2em；首行缩进2个字符

### 文本/内容水平对齐方式

`text-align：；`

| 属性值 | 效果   |
| ------ | ------ |
| left   | 左对齐 |
| right  | 右对齐 |
| center | 居中   |

### 文本修饰

`text-decoration: ;`

| 属性值       | 效果             |
| ------------ | ---------------- |
| underline    | 下划线（常用）   |
| line-through | 删除线           |
| overline     | 上划线           |
| none         | 无装饰线（常用） |

text-decoration：none；清除a标签（超链接）默认的下划线

### 行高

行高：上间距+文本高度+下间距

`line-height: ;`

属性可以为像素或者纯num（自己字号的倍数）

>如果同时设置行高和font连写，注意覆盖问题
>
>font：style weight size/line-height family；

### 颜色

color	background-color

# Chrome调试工具

f12

# 进阶选择器

## 复合选择器

### 后代选择器

```html
父选择器 后代选择器{css}
```

### 子代选择器

```html
父选择器>子选择器{
	css
}
#只选择子选择器里的标签，对其他后代不进行操作	

<body>
    <div>
        父级
        <a href="#">这是div里的a</a>
        <p>
            <a href="#">这是div里的p里的a</a>
        </p>
    </div>
</body>
```

###并集选择器

```html
选择器1,选择器2{css}
#选中多组标签设置相同的样式
```

### 交集选择器

```html
标签.类名{css}
```

### 伪类

```html
选择器：hover{css}
#鼠标悬停时呈现的效果
```

### Emmet语法

`简写语法，快速生成代码`

# 背景

## 背景颜色

`background-color(bgc)：`

## 背景图

`backgrou-image（bgi）：`

### 背景平铺

`background-repeat（bgr）：`

| 取值      | 效果                         |
| --------- | ---------------------------- |
| repeat    | （默认）水平和垂直方向都平铺 |
| no-repeat | 不平铺                       |
| repeat-x  | 沿水平方向（x轴）平铺        |
| repeat-y  | 沿垂直方向（y轴）平铺        |

>背景图在背景色上面

## 背景位置

`background-position（bgp）：水平方向位置 垂直方向位置；`

## 背景相关属性连写

`background(bg):color image repeat position`

==顺序可变！！！==

## 背景图和img的区别

装饰bg，重要img

## 设置背景图片的大小

`background-size：宽度 高度；`

| 取值    | 场景                                                     |
| ------- | -------------------------------------------------------- |
| num+px  | 简单方便，常用                                           |
| 百分比  | 相当于当前盒子自身的宽高百分比                           |
| contain | 包含，将背景图片等比例缩放，直到不会超出盒子的最大       |
| cover   | 覆盖，将背景图片等比例缩放，直到刚好填满整个盒子没有空白 |

# 元素显示模式

## 块

- 独占一行
- 默认宽度是父元素的高度，高度默认由内容撑开
- 可以设置宽高

> div，p，h系列

## 行内

- 一行可以显示多个
- 宽高默认由内容撑开
- 不可以设置宽高

> span，a

## 行内块

- 一行可以显示多个
- 可以设置宽高

> input，textarea，img

`查阅属性的值 maigin的auto 无法作用于行内元素和行内块元素 但是如果是数值可以起作用`

## 显示模式转换

| 属性                  | 效果         |
| --------------------- | ------------ |
| display：block        | 转换成块     |
| display：inline-block | 转换成行内块 |
| display：inline       | 装换成行内   |

## 标签嵌套

块级元素一般作为大容器，可以嵌套文本，块级，行内，行内块…

- 但是：p标签中不能嵌套div，p，h等

a标签可以嵌套任意元素

- 但是：a标签不能嵌套a标签

# css特性

## 继承性

- 文字控制属性都可以继承

继承失效的特殊情况

1. a标签的color会继承失效
2. h标签的font-size会继承失效

## 层叠性

选择器优先级相同时，才通过层叠性判断结果

# css盒子模型

## 优先级

！important>行内样式>id选择器>类选择器>标签选择器>通配符选择器>继承

- ！important写在属性值后面，分号前面
- ！important不能提升继承的优先级，只要是继承优先级最低

### 优先级叠加计算

|      0       |      0       |      0       |        0         |
| :----------: | :----------: | :----------: | :--------------: |
| 行内样式个数 | id选择器个数 | 类选择器个数 | 标签选择武器个数 |

！important如果==不是继承==，则权重最高

## PxCook

[下载链接](https://www.fancynode.com.cn/pxcook)

## 组成

内容区域（content），内边距区域（padding），边框区域（border），外边框区域（margin）

### content宽高

width和height，规定内容所在的范围

### border

`border:粗细 线条样式 线条颜色;`实线：solid；虚线：dashed；点线：dotted

只给盒子某个方向设置边框：border-方位名词

### padding

`padding:上px 右px 下px 左px`

### 自动内减

`box-sizing：border-box；`

### margin

与padding一致

### 清除默认内外边距

```html
*{
	margin:0;
	padding:0;
}
```

### 版心居中

```html
margin:0 auto;
```

### margin问题

#### 合并现象

垂直布局的块级元素，上下的margin会合并，最终两者距离为margin的最大值

#### 塌陷现象

互相嵌套的块级，子元素的margin-top会作用在父元素上

解决方法

1. 给父元素设置border-top或者padding-top（分割父子元素的margin-top）
2. ==给父元素设置overflow：hidden==
3. 转换成行内块元素
4. 设置浮动

### 行内元素的内外边距问题

`如果想要通过margin或padding改变行内标签的垂直位置，无法生效`

# css浮动

## 结构伪类选择器

|          选择器          |                   说明                   |
| :----------------------: | :--------------------------------------: |
|     E：first-child{}     |  匹配父元素中第一个子元素，并且是E元素   |
|     E：last-child{}      | 匹配父元素中最后一个子元素，并且是E元素  |
|   E：nth-child（n）{}    |   匹配父元素中第n个子元素，并且是E元素   |
| E：nth-last-child（n）{} | 匹配父元素中倒数第n个子元素，并且是E元素 |

`E:nth-child(number){css}`number可以为公式

> 当number为公式时，number从0开始

## 伪元素

`由css模拟出的标签效果`

种类

| 伪元素     | 作用                             |
| ---------- | -------------------------------- |
| ：：before | 在父元素内容的最前添加一个伪元素 |
| ：：after  | 在父元素内容的最后添加一个伪元素 |

`必须设置content属性才能生效`

`伪元素默认是行内元素`

```html
E::before{
	content:"内容";
}
```

## 浮动

浏览器在解析行内块或行内标签时，如果标签换行书写会产生一个空格的距离

浮动让div完美的在同一行布局

```html
E{
	float：left/right；
}
```

特点

1. 浮动元素会脱离标准流，在标准流中不占用位置
2. 浮动元素比标准流高半个级别，可以覆盖标准流中的元素
3. 浮动找浮动，下一个浮动会在上一个浮动元素后面左右浮动
4. 浮动元素有特殊的显示效果

- 一行可以显示多个
- 可以设置宽高

`浮动的元素不能通过text-align：center或者margin：0 auto`

## 清除浮动

清除浮动标签给别的标签带来的影响

父子级标签，子集浮动，父级没有高度，后面的标准流盒子会受影响，显示到上面的位置

> 额外标签：

方法：在父元素内容最后添加一个**块级**元素，给添加的块级元素设置`clear：both`，清除左右两侧浮动的影响

缺点：页面添加额外的标签，会让页面的HTML结构变复杂

> 单伪元素清除

```html
.clear::after{
	content:'';
	display:block;
	clear:both;
}
```

> 双伪元素清除
>
> > 即可清浮动又可处理外边距塌陷

```html
.clear::before,
.clear::after{
	content:'';
	display:table;
}
.clearfix::after{
	clear:both;
}
```

> 给父元素设置overflow：hidden

# css书写顺序

1. 定位
2. 浮动/display
3. 盒子模型：margin border padding 宽高背景
4. 文字样式

# 定位

1.标准流

​		1.块级元素独占一行，垂直布局

​		2.行内/行内块元素一行显示多个，水平布局

2.浮动

​		1.可以让原本垂直布局的块级元素变成水平布局

3.定位

​		1.可以让元素自由摆放在网页的任意位置

​		2.一般用于盒子之间的层叠情况

## 设置定位方式

`属性名：position`

| 定位方式 | 属性值   |
| -------- | -------- |
| 相对定位 | relative |
| 绝对定位 | absolute |
| 固定定位 | fixed    |

`设置偏移值`

| 方向 | 属性名 | 属性值 | 含义           |
| ---- | ------ | ------ | -------------- |
| 水平 | left   | num+px | 距离左边的距离 |
| 水平 | right  | num+px | 距离右边的距离 |
| 垂直 | top    | num+px | 距离上边的距离 |
| 垂直 | bottom | num+px | 距离下边的距离 |

## 相对定位

`position:relative;`

```html
div{
	position：relative；
	属性名：属性值；
}
占有原来的位置
仍然具备标签原有的显示模式特点
改变位置参照自己原来的位置
如果left和right都有，以left为准；top和bottom都有，以top为准
不加属性位置不变，不会脱标
```

## 绝对定位

`position:absolute;`

```html
div{
	position：absolute；
	属性名：属性值；
}
先找已经定位的父级，如果有这样的父级就以这个父级为参照物进行定位
有父级，但父级没有定位，以浏览器窗口为参照物进行定位
脱标，不占位置
改变标签的显示模式特点，具备行内块特点：加宽度高度生效，如果没有宽度也没有内容，盒子的宽度尺寸就是0
```

`父级相对定位，子级绝对定位---子绝父相`

### 绝对定位居中

绝对定位的盒子不能使用左右margin auto居中

```html
div{
	position：absolution；
	left：50%；
	margin-left：-一半盒子的宽度；
}
```

### 位移居中

`位移：自己宽度高度的一半`

`transform：translate（-50%，-50%）；`

width：100%；此时子级的宽度和父级一致

## 固定定位

相对于浏览器进行定位移动

`position:fixed;`

脱标，不占位置

具备行内块特点

## 元素层级关系

两个定位的标签 ==后来者居上==

配合z-index属性决定显示层级

z-index：整数；取值越大，显示顺序越靠上，z-index的默认值时0

## 装饰

### 垂直对齐方式

`vertical-align`

| 属性值   | 效果           |
| -------- | -------------- |
| baseline | 默认，基线对齐 |
| top      | 顶部对齐       |
| middle   | 中部对齐       |
| bottom   | 底部对齐       |

浏览器遇到行内和行内块标签当做文字处理，默认文字是按基线对齐

### 光标类型

设置鼠标光标在元素上显示的样式

`cursor`

| 属性值  | 效果                         |
| ------- | ---------------------------- |
| default | 默认值，通常是箭头           |
| pointer | 小手效果，提示用户可以点击   |
| text    | 工字型，提示用户可以选择文字 |
| move    | 十字光标，提示用户可以移动   |

### 边框圆角

`border-radius:num px / 百分比`

赋值规则：从左上角开始赋值，然后顺时针赋值，没有赋值的看对角

> 常见应用：
>
> 正圆
>
> > 盒子必须是正方形
> >
> > border-radius：50%；
>
> 胶囊
>
> >盒子要求是长方形
> >
> >border-radius：盒子高度的一半；

### overflow溢出部分显示效果

`overflow`

| 属性值  | 效果                               |
| ------- | ---------------------------------- |
| visible | 默认值，溢出部分可见               |
| hidden  | 溢出部分隐藏                       |
| scroll  | 无论是否溢出，都显示滚动条         |
| auto    | 根据是否溢出，自动显示或隐藏滚动条 |

### 元素本身隐藏

`visibility：hidden；占位隐藏`

`display：none；不占位隐藏`

### 透明属性opacity

opacity：num；

# 精灵图

1. 创建一个盒子，设置盒子的尺寸和小图尺寸相同
2. 将精灵图设置为盒子的==背景图片==
3. 修改背景图位置
