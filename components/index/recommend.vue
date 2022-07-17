<template>
	<view class="remmend bg-color">
		<view class="recom_item">
			<image src="../../static/bigyifu.png" class="item_big"></image>
			<view class="item_small">
				<image src="../../static/yifuc.jpg" class="item_img"></image>
				<image src="../../static/yifub.jpg" class="item_img"></image>
				<image src="../../static/yifud.jpg" class="item_img"></image>
			</view>
		</view>
		<view class="recom_item">
			<image src="../../static/bigyifub.jpg" class="item_big"></image>
			<view class="item_small">
				<image src="../../static/yifub.jpg" class="item_img"></image>
				<image src="../../static/yifuc.jpg" class="item_img"></image>
				<image src="../../static/yifue.jpg" class="item_img"></image>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss" scoped>
.remmend{
	box-sizing: border-box;
	width: 750rpx;
	padding-top: 2rpx;
	padding-left: 20rpx;
	padding-right: 20rpx;
	padding-bottom: 20rpx;
	.recom_item{
		display: flex;
		flex-direction: column;
		border-radius: 20rpx;
		border: 2rpx solid #ccc;
		overflow: hidden;
		margin-top: 20rpx;
		background-color: white;
		.item_big{
			width: 100%;
			height: 300rpx;
		}
		.item_small{
			display: flex;
			flex-direction: row;
			justify-content: center;
			.item_img{
				height: 240rpx;
				width: 236.66rpx;
				
			}
		}
		
	}
}
</style>
