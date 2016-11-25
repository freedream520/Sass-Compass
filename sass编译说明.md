#### 安装Compass之后，用compass watch 就可以监控sass了，所以并用不到sass编译语句了

命令行编译:
  (如果style.scss文件在D盘中Sass文件夹中,打开Start Command Prompt之后输入dos命令 d: 进入到D盘，然后输入 cd Sass 进入到Sass文件夹中，
    最后输入单个文件转换命令:例如：sass style.scss style.css )
   1. ##### 单文件转换命令
    sass style.scss style.css

   2.单文件监听命令
    sass --watch style.scss:style.css
    (--watch代表一直监听着style.scss?只要在编辑器上更新了scss就会自动更新style.css)

  3.文件夹监听命令
    sass --watch sassFileDirectory:cssFileDirectory

  4.css文件转成sass/scss文件（在线转换工具css2sass）
    sass-convert style.css style.sass
    sass-convert style.css style.scss

  5.SASS提供四个编译风格的选项：
  　　* nested：嵌套缩进的css代码，它是默认值。
  　　* expanded：没有缩进的、扩展的css代码。
  　　* compact：简洁格式的css代码。
  　　* compressed：压缩后的css代码。
    生产环境当中，一般使用最后一个选项。
      sass --style compressed test.scss test.css  注意初次编译需要进入到cd sass计入到sass文件夹中转换，但是compass只需要在项目文件下转换，
      不用进入到sass文件夹下


//好的代码习惯应该是注释占整个篇幅的三分之二。


二. Sass语法介绍(进阶篇):
变量操作:
    1.直接操作变量，即变量表达式。
    2.通过函数。
        1).跟代码块无关的函数，多是自己内置函数，称functions
        2).可重用的代码块，称mixin (有两种方式调用mixin代码块)
            (1)使用时以复制拷贝的方式存在的，在Sass的术语表中称作mixin，通过@include的方式来调用
            (2)使用时以复合声明存在的，我们通过@extend的方式来调用。


