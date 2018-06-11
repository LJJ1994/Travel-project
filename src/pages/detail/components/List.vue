<template>
	<div>
		<div
		 class="item"
		 v-for="(item,index) of List"
		 :key="index">
			<div class="item-title border-bottom">
				<span class="item-title-icon"></span>
				{{ item.title }}
				<div v-if="item.children" class="item-children">
					<detail-list :List="item.children">
					</detail-list>
				</div>
			</div>
		</div>
	</div>
</template>

<script type="text/javascript">
export default {
	name: 'DetailList',
	props: {
		List: Array
	}
}
</script>

<style lang="stylus" scoped>
	.item-title-icon
		position: relative
		display: inline-block
		left: .06rem
		top: .06rem
		width: .36rem
		height: .36rem
		background: url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat
		margin-right: .1rem
		background-size: .4rem 3rem
	.item-title
		line-height: .8rem
		font-size: .32rem
		padding: 0rem .2rem
	.item-children
		padding: 0 .2rem
</style>