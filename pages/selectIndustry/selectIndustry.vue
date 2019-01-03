<template>
	<view class="selectIndustry">
		<!-- 头部 -->
		<!-- #ifndef MP-WEIXIN -->
		<view class="status_bar">
		    <view class="top_view"></view>
		</view>
		<view class="flex page_header">
			<view class="page_header_left">
				<uni-icon type="back" size="18"></uni-icon>
			</view>
			<view class="flex-1 page_header_title">选择行业</view>
			<view class="page_header_right">保存</view>
		</view>
		<!-- #endif -->
		<view class="container">
			<view class="module">
				<view class="filter_module alrSelced">
					<view class="filter_h3 bold">已选择标签 <text class="active">{{alrSelcedArr.length}}/3</text></view>
					<view class="flex filter_ul">
						<view class="filter_li active" v-for="(item,index) in alrSelcedArr" @click="removeLabel(index)">{{item}}<uni-icon type="closeempty" size="24"></uni-icon></view>
					</view>
				</view>
				<view class="filter_module">
					<view class="filter_module_border">
						<view class="filter_h3 bold">互联网/IT/电子/通信</view>
						<view class="flex filter_ul">
							<view class="filter_li">不限</view>
						</view>
					</view>
					<view class="filter_module_border">
						<view class="filter_h3 bold">互联网/IT/电子/通信</view>
						<view class="flex filter_ul">
							<view class="filter_li" v-for="item in 100">广告营销</view>
						</view>
					</view>
				</view>
			</view>
			<!-- #ifdef MP-WEIXIN -->
			<view class="flex footer">
				<button type="primary">保存</button>
			</view>
			<!-- #endif -->
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
	uni-page-head-ft{
		width:100px;
	}
	.footer{
		padding:0 50upx;
		position: fixed;
		bottom:0;
		left:0;
		right: 0;
		height: 130upx;
		background: #fff;
		button{
			width: 100%;
		}
	}
	.selectIndustry{
		.module{
			max-height: 100%;
			padding-bottom: 0;
		}
		.filter_module{
			padding-top: 20upx;
			padding-bottom: 20upx;
			margin-bottom: 10upx;
			background: #fff;
			.filter_h3{
				line-height: 83upx;
			}
		}
		.filter_li{
			line-height: 80upx;
			padding:0 14upx;
			margin-bottom: 20upx;
			margin-right: 20upx;
			min-width: auto;
			background: #f3f3f3;
			border-color: #f3f3f3;
			color:#4a4a4a;
			font-size: 28upx;
			&.active{
				background: #5296f2;
				color:#fff !important;
			}
			
		}
		.alrSelced{
			.filter_li{
				// padding-right: 48urpx
			}
		}
		.filter_module_border{
			margin-bottom: 10upx;
			padding-bottom: 20upx;
			border-bottom: 1px solid #f5f5f5;
			&:last-child{
				border-bottom: none;
			}
		}
	}
</style>
