*  ##HTML 书写规范

```
1. 所使用标签尽量语义化
2. 需要封闭的标签必须封闭
3. 行级元素内部尽量不要嵌套块级元素
4. 元素嵌套的层数尽量少
5. 有特殊含义的标签按标准规范使用
```
* ##css/scss 书写规范

```
1.协作开发及分工：
   根据各个模块，同时根据页面相似程度，事先写好大体框架文件，实现内部结构&表现&行为；
   共用css写成base.css 协作开发过程中，每个页面请务必都要引入，此文件不可随意修改.

2.class 与id 命名：
   *大的框架命名比如header/footer/wrapper/left/right之类统一命名.
   *其他样式名称由小写英文&数字加中划线-小写英文来组合命名，如icon-comment，font-red，width200；
   *避免使用中文拼音，尽量使用简易的单词组合；命名要语义化，简明化。
   *class与id尽量不要重名

3.为JavaScript 预留钩子的命名，请以js_ 起始，比如：js_hide，js_show

4.class 与 id的使用：
   class可用在重复使用率高的模块,class是可以重复的并是子级的，id 是唯一的并是父级的，
   所以id仅使用在大的模块上,JavaScript 预留钩子的除外

5.css 属性书写顺序，建议遵循 布局定位属性-->自身属性-->文本属性-->其他属性。尽量保证同类属性写在一起。
    属性列举：
    布局定位属性主要包括：margin、padding、float(包括clear)、position(相应的top，right，bottom，left)、display、visibility、overflow 等；
    自身属性主要包括：width& height & background & border；
    文本属性主要包括：font、color、text-align、text-decoration、text-indent等；
    其他属性包括：list-style(列表样式)、vertical-vlign、cursor、z-index(层叠顺序) 、zoom 等。我所列出的这些属性只是最常用到的，并不代表全部；

6.书写css代码前，考虑并提高样式重复使用率；充分利用html 自身属性及样式继承原理减少代码量

7.小的背景图片尽量拼接成雪碧图,减少请求量,大的图片尽量使用Png格式,减少图片大小

8. 必须为大区块样式添加注释，小区块适量注释;代码缩进与格式使用编辑器统一风格,增强可读性.
```

* ##javascript 书写规范

```
1.变量命名：驼峰式命名。原生JavaScript变量要求是纯英文字母，首字母须小写，如iTaoLun；jQuery变量要求首字符为'_'，
           其他与原生JavaScript规则相同，如：_iTaoLun；另，要求变量集中声明,避免全局变量,以免冲突
    类命名：首字母大写，驼峰式命名。如 ItaoLun
  函数命名：首字母小写驼峰式命名。如 iTaoLun()

2. 命名语义化，尽可能利用英文单词或其缩写；

3.尽量避免使用存在兼容性及消耗资源的方法或属性，比如eval() & innerText

4.代码结构明了，加适量注释,提高函数重用率,提取公共方法单独存放

5.书写过程中，每行代码结束须有分号(es6编写可省略)；原则上所有功能均根据XXX项目需求原生开发, 
  以避免网上down下来的代码造成的代码污染(沉冗代码||与现有代码冲突|| ...)

6.后期优化中，JavaScript非注释类中文字符须转换成unicode编码使用，以避免编码错误时乱码显示

```

* #注释规范
```
  1.html 注释：注释格式 <!--这儿是注释--> <!--这儿是注释  End-->, '--'只能在注释的始末位置,不可置入注释文字区域；
  2.css 注释：注释格式 /*这儿是注释*/；
  3.JavaScript 注释：单行注释使用'//这儿是单行注释' ，多行注释使用 /* 这儿有多行注释 */；
```

## Build Setup

``` bash
# 安装npm依赖
npm install

# 本地调试模式服务开启 localhost:8080
npm run dev

# 打包压缩合并代码以便发布
npm run build

# 打包到生产 and view the bundle analyzer report
npm run build --report
```
想了解更多,请参考以下文档
[webpack中文文档](https://doc.webpack-china.org/configuration/).
[w3cSchool规范](http://www.w3school.com.cn/html5/index.asp).
[vue中文文档](https://cn.vuejs.org/v2/api/).
[vue-router文档](https://router.vuejs.org/zh-cn/).
[vuex文档](https://vuex.vuejs.org/zh-cn/).

##文件存放位置

``` bash
build--   构建配置文件夹
config--  构建配置初始化文件夹
src--     源代码文件夹
  |--assets 静态资源文件夹
    |--img 图片文件夹
    |--css 样式表文件夹
    |--js  固定引用js文件夹
  |--components 页面所需组件文件夹
    |--scss scss原样式文件夹
  |--service 服务用js工具文件夹
  |--viewPages wepapp各路由子页面文件夹
    |--
  App.vue 单页应用主入口页面
  main.js 单页应用入口js文件
static-- 无需编译直接引用资源文件夹
.babelrc es6转es5配置文件
.gitignore 上传git忽略文件/文件夹
.postcssrc.js css后处理配置
index.html 单页入口html页面
package.json npm打包依赖文件
README.md 工程说明文件
```
