<template>
	<div>
		<div class="title">周末去哪儿</div>
		<ul>
			<li class="item border-bottom"
			 v-for="item in List"
			  :key="item.id"
			>
			  <div class="item-img-wrapper">
					<img class="item-img" :src="item.imgUrl">
				</div>
				<div class="item-info">
					<p class="item-title">{{ item.title }}</p>
					<p class="item-desc">{{ item.desc}}</p>
				</div>
			</li>
		</ul>
	</div>	
</template>

<script type="text/javascript">
export default {
	name: 'HomeWeekend',
	data () {
		return {
			List: [{
				id: '001',
				imgUrl: 'http://img1.qunarzz.com/sight/p0/1805/6f/6f885ea8b30c67bca3.water.jpg_150x150_4abd4a25.jpg',
				title: '水上公园',
				desc: '中国著名的缩微景区'
			},{
				id: '002',
				imgUrl: 'http://img1.qunarzz.com/sight/p0/1805/6f/6f885ea8b30c67bca3.water.jpg_150x150_4abd4a25.jpg',
				title: '水上公园',
				desc: '中国著名的缩微景区'
			},{
				id: '003',
				imgUrl: 'http://img1.qunarzz.com/sight/p0/1805/6f/6f885ea8b30c67bca3.water.jpg_150x150_4abd4a25.jpg',
				title: '水上公园',
				desc: '中国著名的缩微景区'
			},{
				id: '004',
				imgUrl: 'http://img1.qunarzz.com/sight/p0/1805/6f/6f885ea8b30c67bca3.water.jpg_150x150_4abd4a25.jpg',
				title: '水上公园',
				desc: '中国著名的缩微景区'
			}]
		}
	}
}
</script>

<style lang="stylus" scoped>
  .title
    line-height: .8rem
    background: #eee
    text-indent: .2rem
  .item-img-wrapper
    overflow: hidden
    height: 0
    padding-bottom: 37.09%
    .item-img
      width: 100%
  .item-info
    padding: .1rem
    .item-title
      line-height: .54rem
      font-size: .32rem
      overflow: hidden
		  white-space: nowrap
		  text-overflow: ellipsis
    .item-desc
      line-height: .4rem
      color: #ccc
      overflow: hidden
		  white-space: nowrap
		  text-overflow: ellipsis
</style>


