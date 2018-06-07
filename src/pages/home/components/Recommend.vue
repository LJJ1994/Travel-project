<template>
	<div class="recommend">
		<div class="title">热销推荐</div>
		<ul>
			<li class="item border-bottom">
				<img class="item-img" src="http://img1.qunarzz.com/sight/p0/1805/6f/6f885ea8b30c67bca3.water.jpg_150x150_4abd4a25.jpg">
				<div class="item-info">
					<p class="item-title">世界之窗</p>
					<p class="item-desc">中国著名的缩微景区</p>
					<button class="item-button">查看详情</button>
				</div>
			</li>
		</ul>
		<ul>
			<li class="item border-bottom">
				<img class="item-img" src="http://img1.qunarzz.com/sight/p0/1805/6f/6f885ea8b30c67bca3.water.jpg_150x150_4abd4a25.jpg">
				<div class="item-info">
					<p class="item-title">世界之窗</p>
					<p class="item-desc">中国著名的缩微景区</p>
					<button class="item-button">查看详情</button>
				</div>
			</li>
		</ul>
		<ul>
			<li class="item border-bottom">
				<img class="item-img" src="http://img1.qunarzz.com/sight/p0/1805/6f/6f885ea8b30c67bca3.water.jpg_150x150_4abd4a25.jpg">
				<div class="item-info">
					<p class="item-title">世界之窗</p>
					<p class="item-desc">中国著名的缩微景区</p>
					<button class="item-button">查看详情</button>
				</div>
			</li>
		</ul>
		<ul>
			<li class="item border-bottom">
				<img class="item-img" src="http://img1.qunarzz.com/sight/p0/1805/6f/6f885ea8b30c67bca3.water.jpg_150x150_4abd4a25.jpg">
				<div class="item-info">
					<p class="item-title">世界之窗</p>
					<p class="item-desc">中国著名的缩微景区</p>
					<button class="item-button">查看详情</button>
				</div>
			</li>
		</ul>
		<div class="bottom border-bottom">查看所有产品</div>
	</div>	
</template>

<script type="text/javascript">
export default {
	name: 'HomeRecommend'
}
</script>

<style lang="stylus" scoped>
  .title
    margin-top: .2rem
    line-height: .8rem
    background: #fff
    text-indent: .2rem
  .item
    overflow: hidden
    display: flex
    height: 1.9rem
    .item-img
      width: 1.7rem
      height: 1.7rem
      padding: .1rem
    .item-info
      flex: 1
      padding: .1rem
      min-width: 0
      .item-title
        line-height: .54rem
        font-size: .32rem
      .item-desc
        line-height: .4rem
        color: #ccc
      .item-button
        line-height: .44rem
        margin-top: .16rem
        background: #ff9300
        padding: 0 .2rem
        border-radius: .06rem
        color: #fff
  	.bottom
			text-align: center
			margin-top: .2rem
			margin-bottom: .2rem
</style>


