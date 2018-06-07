<template>
	<div class="header">
		<router-link to='/'>
			<div class="iconfont back-header">&#xe624;</div>
		</router-link>
		城市选择
	</div>
</template>

<script type="text/javascript">
export default {
	name: 'Header'
}
</script>

<style lang="stylus" scoped>
	@import '~styles/varible.styl'
	.header
		position: relative
		overflow: hidden
		height: $headerHeight
		line-height: $headerHeight
		text-align: center
		background: #804e9a
		color: #fff
		font-size: .32rem
		.back-header
			position: absolute
			width: .64rem
			font-size: .4rem
			text-align: center
			color: #fff
</style>