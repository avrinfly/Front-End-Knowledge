<!--
 * @Description: 
 * @Author: hetengfei
 * @Github: https://github.com/avrinfly
 * @Date: 2019-10-16 00:00:54
 * @LastEditors: hetengfei
 * @LastEditTime: 2019-10-16 00:00:54
 -->
## 业务背景：
前两天在做业务的时候，突然发现，里边有很多的图片需要去处理，要适应很多不同尺寸的图片，虽然很头痛，做了很多种情况的兼容
## 后续思考：
是否可以找到一种方式，告诉图片应该以什么样的方式展示。比如是一个列表展示图片页，如果图片大小尺寸不一，如何最大程度的还原图片本身，也是一个需要思考的问题

最近找到一个比较好的办法去解决这个问题：
一个CSS属性：**object-fit**

## object-fit

### 概念：
指定可替换元素的内容应该如何适应到其使用的高度和宽度确定的框。

我们也可以通过 ==```object-position```== 属性来切换被替换元素的内容对象在元素框内的对齐方式。

**语法值：**
- **fill**
    
    被替换的内容正好填充元素的内容框。整个对象将完全填充此框。如果对象的宽高比与内容框不匹配，那该对象将被拉伸以适应内容框。
    
- **contain**
    
    被替换的内容将被缩放，以在填充元素的内容框时保持其宽高比。整个对象在填充盒子的同时保留其宽高比，因此如果对象的宽高比和框的宽高比不匹配，该对象将被添加。
- **cover**
    
    被替换的内容在保持其宽高比的同时填充元素的整个内容框。如果对象的宽高比与内容框不匹配，那么该对象会被裁剪以适应内容框。
- **none**
    
    被替换内容保持其原有尺寸。
- **scale-down**
    
    内容的尺寸与```none```或```contain```中的一个相同，取决于它们两个之间谁得到的对象尺寸更小

### 浏览器兼容性

![object-fit属性的浏览器兼容性](https://www.flygoing.cn/images/2019-10-12/object-fit属性的浏览器兼容性.png)

可以看出一个很悲催的点，IE不支持该属性，其他现代浏览器的支持程度还蛮好
如果想把该属性兼容至IE，可点击[这里](https://github.com/anselmh/object-fit)参考


### 不同属性的具体表现
我们先大体看一下，不同属性值最后呈现出来的效果是什么样的
![不同属性的具体表现](https://www.flygoing.cn/images/2019-10-12/不同属性的具体表现.gif)

如果我们想有一个对比的话，可以看下图
![object-fit属性对比图](https://www.flygoing.cn/images/2019-10-12/object-fit属性对比图.png)

以上为不同属性在不同宽高比下(具体来说是2:3和3:2两种宽高比下)的表现

具体内容可查看[这里](https://www.flygoing.cn/views/object-fit-test.html)