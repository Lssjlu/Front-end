# HTML页面结构

```HTML
<html>
    <head>
        <title>网页的标题</title>
    </head>
    <body>
        网页的主体内容
    </body>
</html>
```

# 语法

## 注释

Ctrl + /

## 标签（双，单）

### 标题标签

```html
<body>
    <h1>	</h1>
    <h2>	</h2>
    ...
    <h6>	</h6>
</body>
```

###段落标签

```html
<p>
    段落文字
</p>
```

### 换行标签

```html
文字<br>文字
```

### 水平分割线

```html
文字<hr>文字
```

| 标签 |  说明  |
| :--: | :----: |
|  b   |  加粗  |
|  u   | 下划线 |
|  i   |  倾斜  |
|  s   | 删除线 |

### 图片标签

```html
<img scr="图片路径" alt="图片显示失败时显示该替换文本" title="这是titile文字，鼠标悬停时显示" width="" height="">
width或heigh只设置一个时，另一个等比例缩放
```

> 路径：绝对/相对
> 
> >相对：同级下级and上级

### 音频标签

```html
<audio src="" controls></audio> 
```

|  属性名  |             功能             |
| :------: | :--------------------------: |
| controls |        显示播放的控件        |
| autoplay | 自动播放（部分浏览器不支持） |
|   loop   |           循环播放           |

### 视频标签

```html
<video src="" controls></video>
```

|  属性名  |                      功能                       |
| :------: | :---------------------------------------------: |
| controls |                 显示播放的控件                  |
| autoplay | 自动播放（google浏览器需配合muted实现静音播放） |
|   loop   |                    循环播放                     |

### 超链接

```html
<a href="目标网址/路径" target="_self/_blank">提示文字</a>
_self：默认值，在当前窗口跳转（覆盖原网页）
_blank：在新窗口跳转（保留原网页）
```

## 列表，表格及表单

### 列表

#### 无序列表

```html
<body>
    <ul>
        <li>1</li>
        <li>2</li>
        ...
        <li>n</li>
    </ul>
</body>
```

#### 有序列表

```html
<body>
    <ol>
        <li>1</li>
        <li>2</li>
        ...
        <li>n</li>
    </ol>
</body>
```

#### 自定义列表

```html
<body>
    <dl>
        <dt>主题1</dt>
        <dd>内容1</dd>
        <dd>内容2</dd>
        <dt>主题2</dt>
        <dd>...</dd>
    </dl>
</body>
```

### 表格

#### 基本格式

```html
<body>
    <table border="边框宽度" width="" height="">
        <caption>表格标题</caption>
        <tr>
        	<th>表头单元格</th>
        </tr>
        <tr>
        	<td>1行1列</td>
            <td>1行2列</td>
        </tr>
        <tr>
        	<td>2行1列</td>
            <td>2行2列</td>
        </tr>
    </table>
</body>
```

#### 合并单元格

```html
<body>
     <table border="边框宽度" width="" height="">
        <caption>表格标题</caption>
        <tr>
        	<th>表头单元格</th>
        </tr>
        <tr>
        	<td rowspan="2" colspan="2">1行1列</td>
            #<td>1行2列</td>
        </tr>
        <tr>
        	#<td>2行1列</td>
            <td>2行2列</td>
        </tr>
    </table>
</body>
```

### 表单

#### input

| 标签  | 属性     | 说明                                     |
| ----- | -------- | ---------------------------------------- |
| input | text     | 文本框，用于输入单行文字                 |
| input | password | 密码框，用于输入密码                     |
| input | radio    | 单选框，用于多选一                       |
| input | checkbox | 多选框，用于多选多                       |
| input | file     | 文件选择，用于之后上传文件               |
| input | submit   | 提交按钮，用于提交                       |
| input | reset    | 重置按钮，用于重置                       |
| input | button   | 普通按钮，默认无功能，之后配合js添加功能 |

```html
提示文字：<input type="" placeholder="文本框内提示字">

单选框
<input type="radio" name="" checked>
name将数个单选框分为一组；checked表示该单选框默认选中

文件选择
<input type="file" multiple>
multiple表示上传多个文件

<input type="button" value="按钮内提示文字">
value:修改按钮内提示文字
```

#### 表单域

```html
<form action="">
    #内部的input表单相互关联
</form>
```

#### button按钮标签

| 标签名 | 属性   | 功能     |
| ------ | ------ | -------- |
| button | submit | 提交按钮 |
| button | reset  | 重置按钮 |
| button | button | 普通按钮 |

```html
<button type="">
    按钮内提示文字
</button>
```

#### select下拉菜单

```html
<select>
    <option>内容1</option>
    <option>内容2</option>
    <option>内容3</option>
    <option slected>内容4</option>  #selected:表示该该标签为默认选项
</select>
```

#### textarea文本域标签

```html
<textarea cols="" rows=""></textarea>
```

#### lable标签

```html
<label><input type="" name="">文字</label>
#点击文字也可选择
```

#### 语义化标签

```html
<span>组合行内元素</span>
<div>
    
</div>
```



#### 字符实体

&nbsp；  空格



