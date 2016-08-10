# Markdown 简明指南

**作者: `陈海峰`，本文禁止转载，违者必究**

Markdown 是什么，他能让你以编程的方式写文档，丢掉烦人的格式和样式设置，10分钟便可上手。以后我也能写出漂亮的博客，然后出书啦（支持生成epub，pdf），让我们开始学习吧。

## 简明教程

### 标题

    # 一级标题
    ## 二级标题
    ... 你懂的
    ###### 六级标题
    
    
#### @标题示例

# 最大标题
###### 最小标题


### 列表

    * 这是无序的列表
    * 这是无序的列表2
        * 还可以有子列表哦
    
    1. 这是有序的列表
    1. 这是有序的列表2

#### @列表示例

* 我今天很开心
* 我今天很Happy
    * 额，装B

1. 我喜欢打撸啊撸
1. 我喜欢搓炉石
    1. 特别喜欢法师

### 图片、链接
    
    ![图破了显示这些字](http://mouapp.com/Mou_128.png)
    
    [链接跟图片的区别就在于前面没有那根棒子](http://25.io/mou/)

#### @图片、链接示例

![你看不到我的](http://mouapp.com/Mou_128.png)

听说Mou这个软件很好用，点击[下载](http://25.io/mou/)试试看

![拉风的男人暴露了](http://我很拉风.com)

### 突出
    
    > 这个是引用符号
    
    `仔细看我有背景`
    
    **我好粗**
    
    *我斜哦*


#### @突出示例

> 拉风的男人是要引人注意的

`仔细看我有背景`

**我好粗**

*我斜哦*

### 代码
    
    function hello () {
        console.log('要用tab键（四个空格）缩进')
    }
    
    ```java
    public static void main() {
        System.out.println("这种方式可以指定编程语言，并且可以高亮代码哦");
    }
    ```
#### @代码示例

    function hello () {
        console.log('要用tab键（四个空格）缩进')
    }
    
```java
public static void main() {
    System.out.println("这种方式可以指定编程语言，并且可以高亮代码哦");
}
```
    
### 表格、任务
>  这两种格式不是所有的编辑器都支持哦，因为它不是标准符号
    
       标题       |       描述
    ------- 这里有个竖线 ----------
    表格怎么样    |   我觉得是最复杂的
    表格好用吗    |   尽量少用为妙

    * [x] 我做完她了
    * [ ] 我还没做完
    
#### @表格、任务代码示例

   标题       |       描述
-------       |    ----------
表格怎么样    |   我觉得是最复杂的
表格好用吗    |   尽量少用为妙

* [x] 我做完她了
* [ ] 我还没做完

> Markdown 就这么简单，拉风的男人就照着敲一遍吧。

## 附上其它学习资料

* 推荐 [在线编辑器](http://dillinger.io/) 、有道云协作，github等也支持Markdown

* [认识与入门](http://sspai.com/25137)

* [[知乎]怎样引导新手使用 Markdown？](https://www.zhihu.com/question/20409634)

* [Github Markdown 规范](https://guides.github.com/features/mastering-markdown/)

* [Github 秘籍](https://raw.githubusercontent.com/tiimgreen/github-cheat-sheet/master/README.zh-cn.md)，当作示例好好品读
