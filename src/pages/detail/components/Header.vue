<template>
	<div>
		<router-link
		 tag="div" 
		 to="/" 
		 class="header-abs"
		 v-show="showAbs"
		 >
			<div class="iconfont header-abs-back">&#xe624;</div>
		</router-link>
		<div
		 class="header-fixed" 
		 v-show="!showAbs"
		 :style="styleOpacity">
			<router-link to='/'>
				<div class="iconfont header-fixed-back">&#xe624;</div>
			</router-link>
			景点详情
		</div>
	</div>
</template>

<script>
export default{
	name: 'DetailHeader',
	data () {
		return {
			showAbs: true,
			styleOpacity: {
				opacity: 0
			}
		}
	},
	methods: {
		handleScroll () {
			console.log('scroll')
			const top = document.documentElement.scrollTop
			if(top > 60){
				let opacity = top / 140
				opacity = opacity>1 ? 1: opacity
				this.styleOpacity = {opacity}
				this.showAbs = false
			}else{
				this.showAbs = true
			}
		}
	},
	created () {
		window.addEventListener('scroll', this.handleScroll)
	}
}	
</script>

<style lang="stylus" scoped>
	@import '~styles/varible.styl'
	.header-abs
		position: absolute
		left: .2rem
		top: .2rem
		width: .8rem
		height: .8rem
		line-height: .8rem
		border-radius: .4rem
		background: rgba(0, 0, 0, .8)
		color: #fff
		.header-abs-back
			color: #ccc
			font-size: .4rem
			margin-left: .15rem
	.header-fixed
		position: fixed
		top: 0
		left: 0
		right: 0
		height: $headerHeight
		line-height: $headerHeight
		text-align: center
		background: #00bcd4
		color: #fff
		font-size: .32rem
		.header-fixed-back
			position: absolute
			width: .64rem
			font-size: .4rem
			text-align: center
			color: #fff
</style>