<template>
	<view class="content">
        <view class="header flex">
        	<view class="flex-1 company_name">
        		闽安集团
        	</view>
			<image class="message" src="../../static/message.png" mode=""></image>
			<image class="search" src="../../static/search.png" mode=""></image>
        </view>
		<swiper class="bannerSwiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration" indicator-color="rgba(255,255,255,.35)" indicator-active-color="rgba(255,255,255,1)">
            <swiper-item v-for="item in bannerList">
                <image class="bannerImg" :src="item" mode=""></image>
            </swiper-item>
        </swiper>
		<view class="flex selcType_ul">
			<view class="selcType_li active">福州<text class="triangle"></text></view>
			<view class="selcType_li">行业<text class="triangle"></text></view>
			<view class="selcType_li">排序<text class="triangle"></text></view>
			<view class="selcType_li">筛选<text class="triangle"></text></view>
		</view>
		<!-- 职位 -->
		<view class="job_ul">
			<view class="job_li" v-for="item in [1,2,3,4,5,6]">
				<view class="flex">
					<view class="flex-1 job_name">产品经理</view>
					<view class="salary">3-6K</view>
				</view>
				<view class="flex job_desc">
					<view class="city">
						福州
					</view>
					<view class="edu">
						本科
					</view>
					<view class="exp">
						1-3年
					</view>
				</view>
				<view class="flex company_wrap">
					<image src="../../static/company.png" class="company_img"></image>
					<view class="flex-1">
						<view class="company_name">
							网龙科技有限公司
						</view>
						<view class="company_tro">
							国内上市公司
						</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
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
		}
	}
</script>

<style>
	page{
		background: #f9f9f9;
		/* padding:0 32upx; */
	}
	.header{
		padding:0 32upx;
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
</style>
