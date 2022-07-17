<template>
	<view class="items">
			<image src="../../static/yifue.jpg" class="item_img"></image>
			<view class="item_text">森马短袖T恤女中长款设计感满印宽松休闲风夏季</view>
			<view class="jiage">
				<view class="price">$229</view>
				<view class="oldprice">$269</view>
			</view>
			<view class="zhekou"><text>4.3折</text></view>
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
.items{
			width:375rpx;
			.item_img{
				width:375rpx;
				height:360rpx;
			}
			.item_text{
				line-height: 44rpx;
				font-size: 28rpx;
			}
			.jiage{
				display: flex;
				flex-direction: row;
				line-height:60rpx;
				justify-content:center;
				.price{
					font-weight: 700;
					font-size: 32rpx;
					color:black;
				}
				.oldprice{
					font-size: 30rpx;
					text-decoration: line-through;
					color:#ccc;
					margin-left: 6px;
				}
			}
			.zhekou{
				line-height: 20px;
				font-size: 10px;
				text-align: center;
				color:#bf0f0f;
				box-sizing: border-box;
				padding-bottom: 8px;
				text{
					padding-left: 4rpx;
					padding-right: 4rpx;
					border: 1px solid #bf0f0f;
					border-radius: 12rpx;
				}
			}
		}
</style>
