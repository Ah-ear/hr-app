<template>
	<view class="selectCity">
		<!-- 头部 -->
		<!-- #ifndef MP-WEIXIN -->
		<view class="flex page_header">
			<view class="page_header_left">
				<uni-icon type="back" size="18"></uni-icon>
			</view>
			<view class="flex-1 page_header_title">选择城市</view>
			<view class="page_header_right">保存</view>
		</view>
		<!-- #endif -->
		<view class="container">
			
		</view>
	</view>
</template>

<script>
	import uniIcon from "@/components/uni-icon.vue"
	export default {
		data() {
			return {
				alrSelcedArr:['广告营销','电子商务','游戏'],//已经选择的标签
				
			};
		},
		components:{uniIcon},
		methods:{
			removeLabel(index){
				let arr = [];
				this.alrSelcedArr = this.alrSelcedArr.filter((item,idx) => idx!=index)
			}
		}
	}
</script>

<style scoped lang="less">
	page{
		background: #f5f5f5;
	}
	
</style>
