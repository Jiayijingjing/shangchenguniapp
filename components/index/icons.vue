<template>
	<view class="icons">
		<view class="icons_item">
			<image src="../../static/touxiang.jpg" class="icons_img"></image>
			<text class="icons_name">跑步鞋</text>
		</view>
		<view class="icons_item">
			<image src="../../static/touxiang09.jpg" class="icons_img"></image>
			<text class="icons_name">篮球鞋</text>
		</view>
		<view class="icons_item">
			<image src="../../static/touxiang02.jpg" class="icons_img"></image>
			<text class="icons_name">运动休闲鞋</text>
		</view>
		<view class="icons_item">
			<image src="../../static/touxiang04.jpg" class="icons_img"></image>
			<text class="icons_name">户外鞋</text>
		</view>
		<view class="icons_item">
			<image src="../../static/touxiang05.jpg" class="icons_img"></image>
			<text class="icons_name">运动T恤</text>
		</view>
		<view class="icons_item">
			<image src="../../static/touxiang06.jpg" class="icons_img"></image>
			<text class="icons_name">夹克/连帽衫</text>
		</view>
		<view class="icons_item">
			<image src="../../static/touxiang07.jpg" class="icons_img"></image>
			<text class="icons_name">运动裤</text>
		</view>
		<view class="icons_item">
			<image src="../../static/touxiang08.jpg" class="icons_img"></image>
			<text class="icons_name">冲锋衣裤</text>
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
.icons{
	display: flex;
	flex-direction: row;
	flex-wrap: wrap;
	width:750rpx;
	
	.icons_item{
		display: flex;
		flex-direction: column;
		padding: 20rpx;
		box-sizing: border-box;
		.icons_img{
			width:147.5rpx;
			height: 147.5rpx;
			
		}
		.icons_name{
			font-size: 26rpx;
			text-align: center;
			line-height: 50rpx;
		}
	}
}
</style>
