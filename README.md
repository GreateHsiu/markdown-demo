### markdown 语法介绍

![markdown](icon/markdown.png)

目录：

- [一. 标题](# 一. 标题)
- [二. 区块引用](# 二. 区块引用)
- [三. 修辞和强调](# 三. 修辞和强调)
- [四. 清单](# 四. 清单)
- [五. 连结](# 五. 连结)
- [六. 代码片段](# 六. 代码片段)
- [参考资料](# 参考资料)


# 一. 标题

markdown 支援两种标题的语法，[setext] 1 和 [atx] 2 形式。

*  [setext] 1形式
   
    setext 形式是用底线的形式，利用 `=` （最高阶标题）和 `-` （第二阶标题）
    
	```
	大标题
	=
	
	小标题
	-
	```
    
效果：

大标题
=
小标题
-

*  [atx] 2形式
      
    atx 是在行首插入 1 到 6 个 `#` ，对应到标题 1 到 6 阶。
    ```
	# 一级标题
	
	## 二级标题
	
	### 三级标题
	
	#### 四级标题
	
	##### 五级标题
	
	###### 六级标题
	
	```
效果：

# 一级标题

## 二级标题

### 三级标题

#### 四级标题

##### 五级标题

###### 六级标题

# 二. 区块引用


* 普通区块引用

每个段落的行首加上 ``>``即可

>1.This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

>2.Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse id sem consectetuer libero luctus adipiscing.

* 嵌套区块引用

只要根据层次加上不同数量的``>``
> This is the first level of quoting.
>
> > This is nested blockquote.
>
> Back to the first level.


# 三. 修辞和强调


Markdown 使用星号和下划线来标记需要强调的区段。

```
使用这种符号 *are emphasized*
使用这种符号 _are emphasized also_

使用两个这种符号**strong emphasis**
使用两个这种符号 __use two underscores instead__
```

效果：

使用这种符号 *are emphasized*
使用这种符号 _are emphasized also_

使用两个这种符号**strong emphasis**
使用两个这种符号 __use two underscores instead__


# 四. 清单

无序清单使用星号、加号和减号来做为清单的项目标记，这些符号是都可以使用的，使用星号：

    *   Candy.
    *   Gum.
    *   Booze.

加号：

    +   Candy.
    +   Gum.
    +   Booze.

和减号

    -   Candy.
    -   Gum.
    -   Booze.

都会输出：

*   Candy.
*   Gum.
*   Booze.

有序的清单则是使用一般的数字接着一个英文句点作为项目标记：

    1.  Red
    2.  Green
    3.  Blue

输出：

1.  Red
2.  Green
3.  Blue

如果你在项目之间插入空行，那项目的内容会备用 `<p>` 包起来，你也可以在一个项目内放上多个段落，只要在它前面缩排 4 个空白或 1 个 tab 。

    *   A list item.
    
        With multiple paragraphs.

    *   Another item in the list.

输出：

*   A list item.

    With multiple paragraphs.

*   Another item in the list.



# 五. 连结

Markdown 支援两种形式的连结语法： *行内* 和 *参考* 两种形式，两种都是使用角括号来把文字转成连结。

行内形式形式是直接在后面用括号直接接上连结：

    This is an [example link](http://example.com/).

输出：

This is an [example link](http://example.com/).

你也可以选择性的加上 title 属性：

    This is an [example link](http://example.com/ "With a Title").

输出：

This is an [example link](http://example.com/ "With a Title").


参考形式的连结让你可以为连结定一个名称，之后你可以在文件的其他地方定义该连结的内容：

    I get 10 times more traffic from [Google][1] than from
    [Yahoo][2] or [MSN][3].

    [1]: http://google.com/        "Google"
    [2]: http://search.yahoo.com/  "Yahoo Search"
    [3]: http://search.msn.com/    "MSN Search"

输出：

I get 10 times more traffic from [Google][1] than from
[Yahoo][2] or [MSN][3].

[1]: http://google.com/        "Google"
[2]: http://search.yahoo.com/  "Yahoo Search"
[3]: http://search.msn.com/    "MSN Search"

title 属性是选择性的，连结名称可以用字母、数字和空格，但是不分大小写：

    I start my morning with a cup of coffee and
    [The New York Times][NY Times].

    [ny times]: http://www.nytimes.com/

输出：

I start my morning with a cup of coffee and
[The New York Times][NY Times].

[ny times]: http://www.nytimes.com/


# 五. 图片


图片的语法和连结很像。

行内形式（title 是选择性的）：

    ![alt text](/path/to/img.jpg "Title")

参考形式：

    ![alt text][id]

    [id]: /path/to/img.jpg "Title"

上面两种方法都会输出：

 
![图片无法显示的替代文本](icon/markdown.png "markdown icon")


![图片无法显示的替代文本][image1]

[image1]: icon/markdown.png "markdown icon"

# 六. 代码片段   

在一般的段落文字中，你可以使用反引号 `` ` `` 来标记程式码区段，区段内的 `&`、`<` 和 `>` 都会被自动的转换成 HTML 实体，这项特性让你可以很容易的在程式码区段内插入 HTML 码：

    I strongly recommend against using any `<blink>` tags.

    I wish SmartyPants used named entities like `&mdash;`
    instead of decimal-encoded entites like `&#8212;`.

输出：

I strongly recommend against using any `<blink>` tags.

I wish SmartyPants used named entities like `&mdash;`
instead of decimal-encoded entites like `&#8212;`.

如果要建立一个已经格式化好的程式码区块，只要每行都缩排 4 个空格或是一个 tab 就可以了，而 `&`、`<` 和 `>` 也一样会自动转成 HTML 实体。

Markdown:

    If you want your page to validate under XHTML 1.0 Strict,
    you've got to put paragraph tags in your blockquotes:

        <blockquote>
            <p>For example.</p>
        </blockquote>

输出：

If you want your page to validate under XHTML 1.0 Strict,
you've got to put paragraph tags in your blockquotes:

<blockquote>
    <p>For example.</p>
</blockquote>



# 参考资料：

- [commonmark.org](http://commonmark.org/help/)
- [www.w3school.com.cn](http://www.w3school.com.cn)
- [blog.csdn.net details/52127634](http://blog.csdn.net/qq_20044689/article/details/52127634)













