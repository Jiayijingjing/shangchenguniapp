<template>
	<swiper class="swiper" circular :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval"
		:duration="duration">
		<swiper-item>
			<view class="swiper-item uni-bg-red">
				<image src="../../static/datu.jpg"></image>
			</view>
		</swiper-item>
		<swiper-item>
			<view class="swiper-item uni-bg-green">
				<image src="../../static/zhutu02.jpg"></image>
			</view>
		</swiper-item>
		<swiper-item>
			<view class="swiper-item uni-bg-blue">
				<image src="../../static/zhutu03.jpg"></image>
			</view>
		</swiper-item>
	</swiper>
</template>

<script>
	export default {
	    data() {
	        return {
	            indicatorDots: true,
	            autoplay: true,
	            interval: 2000,
	            duration: 500
	        }
	    },
	    methods: {
	        changeIndicatorDots(e) {
	            this.indicatorDots = !this.indicatorDots
	        },
	        changeAutoplay(e) {
	            this.autoplay = !this.autoplay
	        },
	        intervalChange(e) {
	            this.interval = e.target.value
	        },
	        durationChange(e) {
	            this.duration = e.target.value
	        }
	    }
	}
</script>

<style lang="scss" scoped>
.swiper {
		height: 400rpx;
		width: 750rpx;
}
.swiper-item {
	display: block;
	height: 400rpx;
	line-height: 400rpx;
	text-align: center;
	image{
		width: 100%;
		height: 100%;
	}
}
</style>