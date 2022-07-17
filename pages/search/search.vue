<template>
	<view class="searchmain">
		<view class="beforesearch" >
			<view class="neartitle">最近搜索<view class="delete" @tap="deletelist"><image src="../../static/laji.png"></image></view></view>
			
			<view class="nearsearch"  v-if="searchwords.length > 0">
				<view class="nearitem"  v-for="(item,index) in searchwords" :key="index"> {{item}}</view>
			</view>
			
			<view class="neartitle">热门搜索</view>
			<view class="nearsearch">
				<text class="nearitem">addas</text>
				<text class="nearitem">nike</text>
				<text class="nearitem">面膜</text>
				<text class="nearitem">coach</text>
				<text class="nearitem">四件套</text>
				<text class="nearitem">自营</text>
				<text class="nearitem">施华洛世奇</text>
				<text class="nearitem">MK</text>
			</view>
		</view>
		
	</view>
	
</template>

<script>
	
	export default {
		data() {
			return {
				inputtext:'',
				searchwords:[]
			};
		},
		onLoad() {
			this.keywords = uni.getStorage({
				key:'searchdata',
				success:(res) =>{
					this.searchwords= JSON.parse(res.data);	
				}
			})
		},
		methods:{
			search(e){
				
					if(this.inputtext == ''){
						return uni.showToast({
							title:'关键词不能为空',
							icon:'none'
						})
					}else{
						this.searchwords.push(this.inputtext);
					
						uni.setStorage({
							key:'searchdata',
							data:JSON.stringify(this.searchwords)
						})
						uni.navigateTo({
							url:'/pages/messages/messages?key='+this.inputtext
						})
					}
				
			},
			deletelist(){
				uni.removeStorage({
					key:'searchdata',
					success: (res) =>{
						this.searchwords = [];
					}
				})
			}
		},
		//监听原生标题栏按钮点击事件，参数为Object
		onNavigationBarButtonTap(e){
			if(e.float === 'right'){
				this.search(e);
				
				}
			
		},
		//监听原生标题栏搜索输入框输入内容变化事件
		onNavigationBarSearchInputChanged(e){
			this.inputtext =e.text;
			
		},
		//监听原生标题栏搜索输入框搜索事件，用户点击软键盘上的“搜索”按钮时触发。
		onNavigationBarSearchInputConfirmed(){
			this.search(e);
		}
	}
</script>

<style lang="scss" scoped>
	.searchmain{
		box-sizing: border-box;
		width: 750rpx;
		
		.neartitle{
			padding-left: 20rpx;
			padding-right: 20rpx;
			line-height: 80rpx;
			color: #4a4a4a;
			margin-bottom: 20rpx;
			position: relative;
			.delete{
				padding-left: 20rpx;
				position: absolute;
				right: 40rpx;
				top:16rpx;
				image{
					width: 40rpx;
					height: 40rpx;
				}
			}
		}
		.nearitem{
			display: inline-block;
			box-sizing: border-box;
			border-radius: 40rpx;
			background-color: #ececec;
			margin-left: 40rpx;
			margin-right: 40rpx;
			padding-left: 30rpx;
			padding-right: 30rpx;
			line-height: 60rpx;
			height: 60rpx;
			margin-top: 8rpx;
			margin-bottom: 8rpx;
		}
			
			
	}

</style>
