<template>
	<view class="content">
		<view class="status_bar">
            <view class="top_view"></view>
        </view>
        <view class="header flex">
        	<view class="flex-1 company_name">
        		闽安集团
        	</view>
			<image class="message" src="../../static/message.png" mode=""></image>
			<image class="search" src="../../static/search.png" mode=""></image>
        </view>
		<swiper class="bannerSwiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration" indicator-color="rgba(255,255,255,.35)" indicator-active-color="rgba(255,255,255,1)">
            <swiper-item v-for="item in bannerList" :key="item.id">
                <image class="bannerImg" :src="item" mode=""></image>
            </swiper-item>
        </swiper>
		<view class="wrapper">
			<view class="flex selcType_ul">
				<view :class="{selcType_li:true,active:item.active}" v-for="(item,index) in selcType" :key="item.id" @click="selcTypes(index)">{{item.value}}<text class="triangle"></text></view>
			</view>
			<!-- 弹窗-排序 -->
			<view :class="{toggle_panel:true,hide:!selcType[2].active} ">
				<view class="panel_mask" @click="hideDlg"></view>
				<view class="toggle_panel_content">
					<view :class="{toggle_panel_li:true,active:item.active}" v-for="(item,index) in sortsList" :key="item.id" @click="selcSort(index)">
						{{item.value}}
					</view>
				</view>
			</view>
			<!-- 弹窗-筛选 -->
			<view :class="{toggle_panel:true,hide:!selcType[3].active}">
				<view class="panel_mask" @click="hideDlg"></view>
				<view class="toggle_panel_content">
					<view class="module">
						<view class="filter_module">
							<view class="filter_h3">企业规模</view>
							<view class="flex filter_ul">
								<view class="filter_li">不限</view>
								<view class="filter_li active">1-49人</view>
							</view>
						</view>
						<view class="filter_module">
							<view class="filter_h3">企业规模</view>
							<view class="flex filter_ul">
								<view class="filter_li">不限</view>
							</view>
						</view>
					</view>
					<view class="flex toggle_panel_footer">
						<button type="default">取消</button>
						<button type="primary">确定</button>
					</view>
				</view>
			</view>
			<!-- 职位 -->
			<view class="job_ul">
				<view class="job_li" v-for="item in [1,2,3,4,5,6]">
					<view class="flex">
						<view class="flex-1 job_name">产品经理</view>
						<view class="salary">3-6K</view>
					</view>
					<view class="flex job_desc">
						<view class="city">福州</view>
						<view class="edu">本科</view>
						<view class="exp">1-3年</view>
					</view>
					<view class="flex company_wrap">
						<image src="../../static/company.png" class="company_img"></image>
						<view class="flex-1">
							<view class="company_name">网龙科技有限公司</view>
							<view class="company_tro">国内上市公司</view>
						</view>
					</view>
				</view>
			</view>
			<view class="empty hide">
				<image class="index_empty" src="../../static/index_empty.png" mode=""></image>
				<view class="tip">
					暂无相关职位信息~
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				selcType:[
					{id:1,value:'福州',active:false},
					{id:2,value:'行业',active:false},
					{id:3,value:'排序',active:false},
					{id:4,value:'筛选',active:false}
				],
				sortsList:[
					{id:1,value:'按时间排序',type:0,active:false},
					{id:2,value:'按薪资排序',type:1,active:false}
				],//排序
				title: 'Hello',
				bannerList: [
					'../../static/banner.png',
					'../../static/banner.png',
					'../../static/banner.png',
				],
				indicatorDots: true,
				autoplay: false,
				interval:5000,
				duration:1000
			}
		},
		onLoad() {

		},
		methods:{
			//筛选
			selcTypes(index){
				this.selcType.forEach(item => {
					item.active = false;
				})
				this.selcType[index].active = !this.selcType[index].active
			},
			//排序
			selcSort(index){
				this.sortsList.forEach(item => {
					item.active = false;
				})
				this.sortsList[index].active = true;
				this.hideDlg();
			},
			hideDlg(){
				this.selcType.forEach(item => {
					item.active = false;
				})
			}
		},
		computed:{
			
		}
	}
</script>

<style  lang="less" scoped>
	
	page{
		background: #f9f9f9;
		/* padding:0 32upx; */
	}
	.header{
		padding:0 32upx 18upx;
		line-height: 86upx;
		background: #fff;
	}
	.header .company_name{
		font-size: 40upx;
		font-weight: bold;
	}
	.message{
		padding:0 23upx;
		width: 40upx;
		height:40upx;
	}
	.search{
		padding-left:23upx;
		width: 40upx;
		height:40upx;
	}
	.bannerSwiper{
		padding:0 32upx;
		height:200upx;
		background: #fff;
	}
	.bannerImg{
		width: 100%;
		height:200upx;
		border-radius: 6upx;
	}
	.index_empty{
		display: block;
		margin:200upx auto 85upx;
		width: 351upx;
		height:256upx;
	}
	.tip{
		text-align: center;
		font-size: 28upx;
		color:#666;
		line-height: 1;
	}
</style>
