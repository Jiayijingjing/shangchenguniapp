<template>
	<view class="cards">
		
		<view class="card_name">- 猜你喜欢 -</view>
		<view class="card_item">
			<commoditys></commoditys>
			<commoditys></commoditys>
			<commoditys></commoditys>
			<commoditys></commoditys>
		</view>
	</view>
</template>

<script>
	import commoditys from "./commodity.vue"
	export default {
		data() {
			return {
				
			}
		},
		components:{
			commoditys
		}
	}
</script>

<style lang="scss" scoped>
.cards{
	
	.card_name{
		text-align: center;
		height: 90rpx;
		line-height: 90rpx;
		font-size: 40rpx;
	}
	.card_item{
		display: flex;
		flex-direction: row;
		flex-wrap:wrap;
		width: 100%;
		justify-content:space-between;
	}
}
</style>
