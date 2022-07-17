<template>
	<view>
		<cards></cards>
		<cards></cards>
	</view>
</template>

<script>
	import cards from '../../components/common/cards.vue'
	export default {
		data() {
			return {
				keyword:''
			};
		},
		components:{
			cards
		},
		props:{
			
		},
		onLoad(e) {
			this.keyword = e.key;
			
			// #ifdef APP-PLUS  
			console.log('22222')
			var webView = this.$mp.page.$getAppWebview();  
			// 设置 searchInput的 text  
			webView.setTitleNViewSearchInputText(e.key)  
			
			// #endif
		    
		
		}
	}
</script>

<style lang="scss">

</style>
