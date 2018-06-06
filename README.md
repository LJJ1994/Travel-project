# travel

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report







一、制作首页的内容header

1.安装stylus 和stylus loader  css预编译语言

1rem = html font-size 50px

2.利用stylus自定义css变量，以达到优化css的目的

3.修改webpack的路径配置，减少路径的复杂使用，然后重启服务器




二、首页轮播图

1.借助轮播插件vue-awesome-swiper

在https://github.com/surmon-china/vue-awesome-swiper下

npm install vue-awesome-swiper@2.6.7 --save

2.问题：在轮播途中，给轮播图的灰色点号加css样式报错

	.wrapper >>> .swiper-pagination-bullet-active
    background: #fff

3.用vuejs中的v-for对轮播图进行循环输出，在返回的data中的swiperOption，利用loop属性，设置为true，可以进行左右循环输出。

4.计算属性
利用计算属性计算已有的属性值
computed: {
      pages () {
        const pages = []
        this.iconList.forEach((item,index) => {
          const page = Math.floor(index/8)
          if(!pages[page]) {
            pages[page] = []
          }
          pages[page].push(item)
        })
        return pages
      }
    }
此例中用一个pages数组判断当前index值是否在当前page页，如果存在当前page页，则返回该值的上取整数；
如果不存在，则置数组为空，返回数组。

5.css技巧

		overflow: hidden
    white-space: nowrap
    text-overflow: ellipsis

利用该组合，如果当前内容溢出，则末尾有显示省略号(...)。


GIT合并分支工作流程：

git add .

git commit -m '轮播图制作'

git push

git checkout master

git merge origin/index-swiper

git push




