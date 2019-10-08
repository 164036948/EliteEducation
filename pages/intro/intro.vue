<template>
	<view>
		<view class="top">
			<swiper class="swiper" circular :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
				<swiper-item>
					<view class="swiper-item">
						<image src="../../static/EliteEducation.jpg" mode="scaleToFill" style="height: 450rpx; width: 100%;"></image>
					</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item uni-bg-green">B</view>
				</swiper-item>
			</swiper>
		</view>
		<view class="center uni-flex uni-column">
			<view class="center_top uni-flex uni-row " style="-webkit-align-items: center;align-items: center;">
				<text style="font-weight: 700; font-size: 30rpx;">公司简介</text>
			</view>
			<view class="center_center " >
				<text>在做企业咨询服务的这些日子里,发现个有趣的现象,那就是各企业的都存在供需双方的矛盾,企业有人才需求,但是合适的人才都进不来,人才有需求,但是人才永远找不到合适的东家做搭档;这是人才要求高?我觉得这些都不是,而是各自对自身定位不准确的问题。企业希望人才全能...</text>
			</view>
			<view class="center_down" style="align-self: flex-end ;-webkit-align-self: flex-end ;">
				<text style="color: red;">查看更多>></text>
			</view>
		</view>
		<view class="down">
			<view class="down_top uni-flex uni-row " style="-webkit-align-items: center;align-items: center;">
				<text style="font-weight: 700; font-size: 30rpx;">新闻动态</text>
			</view>
			<view class="down_down">
				<view class=""></view>
				<view class="">
					<view class=""></view>
					<view class=""></view>
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
				duration: 500
			}
		},
		methods: {
			
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
		line-height: 38rpx;
		font-size: 30rpx;
		overflow:hidden;
		text-overflow:ellipsis;
		padding-left: 50rpx;
	}
	.center_down{
		padding-right: 20rpx;
	}
	.down{
		padding-top: 10rpx;
	}
	.down_top{
		background-color: #FFFFFF;
		height: 70rpx;
		padding-left: 30rpx;
	}
</style>
