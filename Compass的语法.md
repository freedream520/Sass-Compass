1. ##### Comapss是一个强大的Sass框架，内置大量的实用功能，可以简化Sass的开发。
    Compass文件夹是在ruby里通过 mkdir compassFileName 创建的，
    然后进入到(cd compassFileName)中 compass create abc创建 一个文件夹为abc的sass项目。

2. ##### Compass安装 : sass和compass都是依赖Ruby的，第一步肯定是安装ruby，教程见sass安装书签
    (Ruby的安装：下载后就按照这个网址  http://www.w3cplus.com/sassguide/install.html 的安装步骤安装就好了)
    windows平台下使用RubyGems安装
       (1)使用gem安装Compass
            gem install compass
       (2)测试Compass
            compass version //记得都是在Ruby里测试的
       (3)Devkit的下载和安装(出现ffi错时的解决方案)
            -到rubyinstaller.org下载Devkit
            -解压到本地，进行安装

3. ##### compass编译(compass 编译只需要在项目文件夹下转换，不需要进入到sass文件夹中，但是sass语法单独转换则需要进入到sass文件夹中)
    Compass的编译命令是compass compile  该命令在项目根目录下运行，会将sass子目录中的scss文件，编译成css文件，保存在stylesheets子目录中。
    1.compass编译.scss文件后的四中样式
        SASS提供四个编译风格的选项：
            　　* nested：嵌套缩进的css代码，它是默认值。
            　　* expanded：没有缩进的、扩展的css代码。
            　　* compact：简洁格式的css代码。
            　　* compressed：压缩后的css代码。
    2.默认状态下，编译出来的css文件带有大量的注释。但是，生产环境需要压缩后的css文件，这时要使用--output-style参数。
       语法: compass compile --output-style compressed

4. ##### compass取消注释
    1、打开项目根目录下的 config.rb 文件
    2、搜索 line_comments 关键词，默认应该是 # line_comments = false
    3、去掉前面的 #，保存 config.rb
    4、重新执行 compass compile
    这样编译出来的 css 文件中就不会包含自动生成的行注释信息了。


5. #####Compass常用命令
    compass create   :  创建新Compss项目
    compass init     :  为已存在项目添加compass
    compass clean    :  移除已生成的文件和缓存
        //比如手动输入 compass clean 可以把abc文件夹下面的子文件夹stylesheets中的三个css文件删除
    compass compile  :  生成样式表文件
        //上面通过 compass clean 手动删除stylesheets中的三个css文件之后可以运行这行代码在从新生成三个css文件。
    compass watch    :  监视sass文件并自动编译:
        //这个比如说abc项目中的scress.scss修改了代码之后styelesheets并没有更新的话，那就可以用 compass watch
         手动更新就可以了。
    compass stats    :  查看样式表统计数据
    compass validate :  验证生成的css文件

6. ##### 用compass创建一个sass项目，现在就以compass文件夹下的compassTest项目为例
    打开Ruby Command Prompt输入命令: "d:" 进入到D盘，
    然后输入 "cd Sass" 转到Sass文件夹，输入 "cd Compass" 进入到Compass文件夹，
    然后输入 "mkdir compassTest"创建compassTest文件夹，
    然后输入 "cd com*(或者是compassTest)"进入到新创建的compassTest文件夹里，
    然后输入 "compass create abc" 这样就创建了一个名称为abc的sass项目

7. ##### compass使用时候的一些语法都在screen.scss文件里面(就是在compassTest/abc/sass/screen.scss文件里)

8. ##### Compass分为6大模块：
    (1)Reset模块: reset模块和下面的layout模块是需要用单独的@import导入的模块，然后在需要的class和id中用@include method(参数)。
    (2)Layout模块: 页面布局
    (3)Css3模块： 注释:css3模块,helpers模块，typography模块和utilities模块这几个模块在 @import "compass" 
        导入compass之后不需要单独引入了，当然如果不直接引入compass单独引入每个子模块也是可以的。 css3模块主要提供css3的跨浏览器能力
    (4)Helpers模块
    (5)Typography模块: /ta?'p?gr?f?/ 字体，排版，印刷
    (6)Utilities模块: /ju?'t?l?t?/实用
    ###### Reset模块 :
          Reset的核心Mixin： //mixin是sass中混合宏的概念详细见"Sass语法讲解和示例"这个文件
              global-reset          全局重置
              nested-reset          嵌套重置
              reset-box-model       重置盒模型
              reset-font            重置字体
              reset-body            重置body主题
              reset-html5           重置html5的部分
              reset-list-style      重置list-style样式
              reset-table           重置table
              reset-table-cell      重置表格单元格
              reset-quotation       重置索引
              reset-image-anchor-border 重置图像锚点边框
              reset-display($selector, $important) 重置display
              reset-focus           重置focus焦点                     
    ###### Layout模块: layout模块用来提供页面布局的控制能力，比如说将一个容器内的子元素横向拉伸纵向拉伸占占满。 layout模块必须单独引入才能生效
        layout模块提供了是三个功能模块分别为：（注释:使用率不是很高）
            (1) @import "compass/layout/grid-background";
            (2) @import "compass/layout/sticky-footer";
                :sticky-footer模块，提供footer总在页面最底部的解决方案，但是需要固定结构：
                    <body>
                        <div id="root">
                            <div id="root_footer"></div>
                        </div>
                        <div id="footer">
                            Footer content goes here.脚注内容放这里
                        </div>
                    </body> //html代码
                    使用代码: @include sticky-footer(30px); //参数为footer的高度
            (3) @import "compass/layout/stretching";
    ###### CSS3模块 :  在需要的class和id中用@include method(参数) [如果没有参数直接写方法名也是可以的比如 @include rest-box-model] 就可以了。
    ###### Helpers模块: 同3。
    ###### Typography模块: 同3。typography /ta?'p?gr?f?/ 字体，排版，印刷
        typography模块又细分为4个核心mixin模块，可以分别引入
            @import "compass/typrography/links"
            @import "compass/typrography/lists"
            @import "compass/typrography/text"
            @import "compass/typrography/vertical-rhythm"
    ###### Utilities模块: 同3。 utility /ju?'t?l?t?/实用
