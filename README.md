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

3.用vuejs中的v-for对轮播图进行循环输出，在返回的data中的swiperOption，利用loop属性，设置为true，可

以进行左右循环输出。

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

6.ajax获取首页数据

分析：如果一个大组件里面的每个小组件都发送ajax请求，把对应的数据拿过来，那么会造成网站性能问题。

所以应该在大组件里面发送ajax请求，然后将这些请求发送给所包含的小组件。使用axios必须在大组件引

入axios，如下：

import axios from 'axios'

methods: {
    getHomeInfo () {
      axios.get('/api/index.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc(res){
      console.log(res)
    }
  },
  mounted () {
    this.getHomeInfo()
  }

7.首页父子组件数据传递

首先定义后台json文件，然后在大组件Home.vue里定义一个mounted钩子函数，如下：

mounted () {
    this.getHomeInfo()
  }

然后在methods里定义函数，利用aixos中的get方法，获取json文件里面的数据，如下：

methods: {
    getHomeInfo () {
      axios.get('/api/index.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {//如果json允许传值，且数据存在
        const data = res.data //将传入的数据保存在一个变量里，以便提高性能
        this.city = data.city
        this.SwiperList = data.swiperList 
        this.IconsList = data.iconList
        this.RecommendList = data.recommendList
        this.WeekendList = data.weekendList
      }
    }
  }

  利用props特性，父组件向子组件传值。

  1.首先在返回的数据里定义数组，用来接收json传回的值，然后在子组件模板绑定自定义属性，将父组

  件的值传给该属性，如下：

  <template>
  <div>
    <home-header :city="city"></home-header>
    <home-swiper :swiper="SwiperList"></home-swiper>
    <home-icons :list="IconsList"></home-icons>
    <home-recommend :list="RecommendList"></home-recommend>
    <home-weekend :list="WeekendList"></home-weekend>
  </div>
	</template>

  data () {
    return {
      city: '',
      SwiperList: [],
      IconsList: [],
      RecommendList: [],
      WeekendList: []
    }
  }

  2.在子组件里，利用props接收父组件传过来的值，并设置该值的数据类型

  export default{
	  name: 'HomeHeader',
	  props: {
	    city: String
	  }
	}


8.城市路由选择

1.在header首页，使用 <router-link to='/city'> 进行页面跳转

9.搜索框制作

10.城市选择页面列表布局

使用better-scroll实现城市列表的上下滚动

npm install better-scroll --save

使用方法：

	import BScroll from 'better-scroll'
	const wrapper = document.querySelector('.wrapper')
	const scroll = new BScroll(wrapper)

11.页面动态数据渲染

	通过ajax获取后台json数据。

	json里的cities的类数组，包含着许多对象，一个对象里面包含着多个属性，那么利用v-for对城市列表进行两

  次循环。如下：

	<div class="area" v-for="(item,key) in cities">
		<div class="title border-topbottom">{{ key }}</div>
		<div class="item-list" v-for="innerItem in item" :key="innerItem.id">
			<div class="item border-bottom">{{ innerItem.name }}</div>
		</div>
	</div>

12.城市搜索功能实现

  在搜索框输入关键字时，界面显示搜索内容，并且内容可以滚动显示。

  1.当输入关键字时，如果有对应的城市或者相似的城市，那么列表显示内容；否则显示无法匹配到该内容

  2.当不输入关键字时，那么搜索列表框关闭

  3.用v-model实现input输入框和数据的双向绑定。


13.Vuex实现首页和城市选择数据共享

实现功能： 点击城市列表里面的城市时，首页header的城市名跟着改变

利用vuex的里的state、actions、mutations实现

另外，当点击城市时，利用vue.router的编程式导航，跳转到指定的页面，如下：

router.push(location, onComplete?, onAbort?)

14.动态路由渲染及详情页制作

问题：加入的router-vue不能正常渲染

解决： 在webpack配置中，加入common.js

export.modules =
  {
    alias: {
        'common': resolve('src/common')
      }
  }

15.公共画廊组件制作

重点！！






















































GIT合并分支工作流程：

git add .

git commit -m '轮播图制作'

git push

git checkout master

git merge origin/index-swiper

git push

Git拉取分支

git pull

git checkout index-xxx //git 切换到该分支

git status 




