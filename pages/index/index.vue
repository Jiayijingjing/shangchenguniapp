<template>
	<view class="main">
		<!-- #ifdef MP-WEIXIN -->
		<!-- <view class="wn_nav">
			<view class="iconfont icon-fangdajing"></view>
			<view >百年奥莱</view>
			<view class="iconfont icon-xiaoxi"></view>
		</view> -->
		<!-- #endif -->
		<scroll-view class="scroll-view_H" scroll-x="true"  scroll-left="0" :scroll-into-view="scrollindex" >
			<view id="demo0" class="scroll-view-item_H" @tap="headbar(0)" :class="topbar === 0?'blue':'' ">推荐</view>
			<view id="demo1" class="scroll-view-item_H" @tap="headbar(1)" :class="topbar === 1?'blue':'' ">运动户外</view>
			<view id="demo2" class="scroll-view-item_H" @tap="headbar(2)" :class="topbar === 2?'blue':'' ">服饰内衣</view>
			<view id="demo3" class="scroll-view-item_H" @tap="headbar(3)" :class="topbar === 3?'blue':'' ">鞋靴箱包</view>
			<view id="demo4" class="scroll-view-item_H" @tap="headbar(4)" :class="topbar === 4?'blue':'' ">美妆个护</view>
			<view id="demo5" class="scroll-view-item_H" @tap="headbar(5)" :class="topbar === 5?'blue':'' ">家居数码</view>
			<view id="demo6" class="scroll-view-item_H" @tap="headbar(6)" :class="topbar === 6?'blue':'' ">食品母婴</view>
		</scroll-view>
		<swiper class="swipera" circular   :current="tabcurrent" @change="changetopbar" :style="{height:clientheight+'px'}">
			<swiper-item class="swiper-itema" >
				<scroll-view scroll-y="true" :style="{height:clientheight+'px'}" @scrolltolower="loadmore" >
					<swipers></swipers>
					<recommend></recommend>
					<cards ></cards>
					<view class="bottomload">{{loadtext}}</view>
				</scroll-view>
			</swiper-item>
			<swiper-item class="swiper-itema" >
				<scroll-view scroll-y="true" :style="{height:clientheight+'px'}" @scrolltolower="loadmore">
					<banner></banner>
					<coins></coins>
					<cards ></cards>
					<view class="bottomload">{{loadtext}}</view>
				</scroll-view>
			</swiper-item>
			<swiper-item class="swiper-itema" >
				<scroll-view scroll-y="true" :style="{height:clientheight+'px'}" @scrolltolower="loadmore">
					<banner></banner>
					<cards ></cards>
					<view class="bottomload">{{loadtext}}</view>
				</scroll-view>
			</swiper-item>
			<swiper-item class="swiper-itema" >
				<scroll-view scroll-y="true" :style="{height:clientheight+'px'}" @scrolltolower="loadmore">
					<banner></banner>
					<cards ></cards>
					<view class="bottomload">{{loadtext}}</view>
				</scroll-view>
			</swiper-item>
			<swiper-item class="swiper-itema" >
				<scroll-view scroll-y="true" :style="{height:clientheight+'px'}" @scrolltolower="loadmore">
					<banner></banner>
					<cards ></cards>
					<view class="bottomload">{{loadtext}}</view>
				</scroll-view>
			</swiper-item>
			<swiper-item class="swiper-itema" >
				<scroll-view scroll-y="true" :style="{height:clientheight+'px'}" @scrolltolower="loadmore">
					<banner></banner>
					<cards ></cards>
					<view class="bottomload">{{loadtext}}</view>
				</scroll-view>
			</swiper-item>
			<swiper-item class="swiper-itema" >
				<scroll-view scroll-y="true" :style="{height:clientheight+'px'}" @scrolltolower="loadmore">
					<banner></banner>
					<cards ></cards>
					<view class="bottomload">{{loadtext}}</view>
				</scroll-view>
			</swiper-item>
		</swiper>
		
	</view>
</template>

<script>
	import swipers from '../../components/index/indexSwiper.vue'
	import recommend from '../../components/index/recommend.vue'
	import cards from '../../components/common/cards.vue'
	import banner from '../../components/index/banner.vue'
	import coins from '../../components/index/icons.vue'
	export default {
		data() {
			return {
				topbar:0,
				tabcurrent:0,
				scrollindex:'demo0',
				clientheight:0,
				loadtext:'触底加载中...'
				
			}
		},
		components:{
			swipers,
			recommend,
			cards,
			banner,
			coins
		},
		onLoad() {
			
		},
		onReady() {
			uni.getSystemInfo({
				success:(res) => {
					this.clientheight = res.windowHeight-uni.upx2px(80)-2;
					
				}
			})
		},
		onNavigationBarButtonTap(e){
			if(e.index == 0){
				uni.navigateTo({
					url:'/pages/search/search'
				})
			}else if(e.index == 1){
				uni.navigateTo({
					url:'/pages/messages/messages'
				})
			}
		},
		methods: {
			//顶栏滑动
			headbar(index){
				if(index == this.topbar){
					return
				}
				this.topbar = index;
				this.tabcurrent = index;
				this.scrollindex = 'demo'+index;
				this.loadtext  = '触底加载中...';
			},
			//swiper插件
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
			},
			changetopbar(e){
				this.headbar(e.detail.current);
			},
			loadmore(){
				const timer = setTimeout(()=>{
					clearTimeout(timer);
					this.loadtext  = '';
				},1000)
			}
			
			
		}
	}
</script>

<style scoped lang="scss">
.swipera {
		width: 750rpx;
}
.swiper-itema {
	display: block;
	text-align: center;
	.bottomload{
		line-height: 100rpx;
		background-color: #f8f8f8;
	}
}
// .wn_nav{
	// 	height: 200rpx;
	// 	width: 100%;
	// 	line-height: 200rpx;
	// 	text-align: center;
	// 	display: flex;
	// 	justify-content: space-between;
	// 	align-items: center;
	// 	padding-left: 8px;
	// 	padding-right:8px;
	// }
	.scroll-view_H {
			white-space: nowrap;
			padding-bottom: 10rpx;
		.scroll-view-item {
			text-align: center;
			font-size: 16rpx;
		}
		.scroll-view-item_H {
			display: inline-block;
			padding-left: 14rpx;
			padding-right: 14rpx;
			height: 70rpx;
			line-height: 70rpx;
			text-align: center;
			font-size: 26rpx;
			color:#767676;
		}
		.blue{
			border-bottom: 2px solid #2aaddc;
			color:#2aaddc;
		}
		
	}
</style>
