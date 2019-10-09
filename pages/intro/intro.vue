<template>
	<view>
		<!-- 顶部图片轮换 -->
		<view class="top">
			<swiper class="swiper" circular :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
				<swiper-item>
					<view class="swiper-item">
						<image src="../../static/EliteEducation.jpg" mode="scaleToFill" style="height: 450rpx; width: 100%;"></image>
					</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item uni-bg-green">
						<image src="../../static/EliteEducation.jpg" mode="scaleToFill" style="height: 450rpx; width: 100%;"></image>
					</view>
				</swiper-item>
			</swiper>
		</view>
		<!-- 中间区块 -->
		<view class="center uni-flex uni-column">
			<!-- 标题文字 -->
			<view class="center_top uni-flex uni-row " style="-webkit-align-items: center;align-items: center;">
				<text style="font-weight: 700; font-size: 35rpx;">公司简介</text>
			</view>
			<!-- 主要文本内容 -->
			<view class="center_center " >
				<text>在做企业咨询服务的这些日子里在做企业咨询服务的这些日子里在做企业咨询服务的这些日子里在做企业咨询服务的这些日子里//在做企业咨询服务的这些日子里,发现个有趣的现象,那就是各企业的都存在供需双方的矛盾,企业有人才需求,但是合适的人才都进不来,人才有需求,但是人才永远找不到合适的东家做搭档;这是人才要求高?我觉得这些都不是,而是各自对自身定位不准确的问题。企业希望人才全能...</text>
			</view>
			<!-- 红色字体跳转详情 -->
			<view @click="opendetails" class="center_down" style="align-self: flex-end ;-webkit-align-self: flex-end ;">
				<text style="color: red;">查看更多>></text>
			</view>
		</view>
		<!-- 底部模块 -->
		<view class="down">
			<!-- 标题文字 -->
			<view class="down_top uni-flex uni-row " style="-webkit-align-items: center;align-items: center;">
				<text style="font-weight: 700; font-size: 35rpx;">新闻动态</text>
			</view>
			<!-- 循环输出新闻动态的标签 -->
			<view v-for="(downcontent,index1) in downcontents" :key="index1" class="down_down uni-flex uni-row" style="-webkit-align-items: center;align-items: center;">
				<!-- 标签的图片 -->
				<view class="down_image">
					<image :src="downcontent.imagesrc" mode="scaleToFill" style="height: 160rpx; width: 220rpx;"></image>
				</view>
				<!-- 左侧的文字 -->
				<view class="down_text uni-flex uni-column" style="-webkit-flex: 1;flex: 1;">
					<view class="down_text_top">
						<text style="font-weight: 700; font-size: 35rpx; ">{{downcontent.contenttext}}</text>
					</view>
					<!-- 跳转页面 -->
					<view @click="opennews(index1)" class="down_text_down" style="align-self: flex-end ;-webkit-align-self: flex-end ;">
						<text style="color: red;" >{{downcontent.jumptext}}</text>
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
				indicatorDots: true,
				autoplay: true,
				interval: 2000,
				duration: 500,
				downcontents : [{
					contenttext : '休闲娱乐中心,以对员工正式开放',
					jumptext : '查看详情>>',
					imagesrc : '../../static/e2.jpg',
					jumpurl : '../news/news'
				},
				{
					contenttext : '休闲娱乐中心,以对员工正式开放',
					jumptext : '查看详情>>',
					imagesrc : '../../static/e1.jpg',
					jumpurl : '../news/news'
				}]
			}
		},
		methods: {
			opennews(e){
				uni.navigateTo({
					url: this.downcontents[e].jumpurl
				});
			},
			opendetails(){
				uni.navigateTo({
					url: '../details/details'
				});
			}
		}
	}
</script>

<style>
	page{
		background-color: #ededed;
	}
	.swiper {
		height: 450rpx;
	}
	.swiper-item {
		height: 450rpx;
	}
	.center{
		background-color: #fff;
	}
	.center_top{
		padding-left: 30rpx;
		height: 75rpx;
	}
	.center_center{
		width: 660rpx;
		height: 230rpx;
		line-height: 39rpx;
		font-size: 30rpx;
		overflow:hidden;
		text-overflow:ellipsis;
		padding-left: 50rpx;
		color: #666;
	}
	.center_down{
		padding-right: 20rpx;
		padding-bottom: 25rpx;
	}
	.down{
		padding-top: 10rpx;
	}
	.down_top{
		background-color: #FFFFFF;
		height: 43rpx;
		padding-left: 30rpx;
		padding-top: 30rpx;
	}
	.down_down{
		background-color: #FFFFFF;
		height: 218rpx;
	}
	.down_image{
		padding-left: 30rpx;
	}
	.down_text{
		padding-left: 30rpx;
	}
	.down_text_top{
		width: 405rpx;
	}
	.down_text_down{
		padding-right: 20rpx;
	}
</style>
