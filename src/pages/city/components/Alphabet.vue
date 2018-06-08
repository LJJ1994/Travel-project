<template>
	<div class="list">
		<ul>
			<li class="item"
			 v-for="(item,key) of cities"
			 @click="handleLetterClick"
			>
				{{ key }}
			</li>
		</ul>
	</div>
</template>

<script type="text/javascript">
export default {
	name: 'CityAlphabet',
	props: {
		cities: Object
	},
	methods: {
		handleLetterClick (e) {
			this.$emit('change',e.target.innerText)
		}
	}
}
</script>

<style lang="stylus" scoped>
	.list
		position: absolute
		display: flex
		flex-direction: column
		justify-content: center
		top: 1.5rem
		right: 0
		bottom: 0
		width: .4rem
		background: #a0daba26
		.item
			line-height: .4rem
			text-align: center
			color: black
</style>