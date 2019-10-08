<template>
	<view>
		<view class="top">
			<swiper class="swiper" circular :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
				<swiper-item>
					<view class="swiper-item">
						<image src="../../static/EliteEducation.jpg" mode="scaleToFill" style="height: 300rpx; width: 100%;"></image>
					</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item uni-bg-green">B</view>
				</swiper-item>
			</swiper>
		</view>
		<view class="center uni-flex uni-row">
			<view class="center-left uni-flex" style="-webkit-justify-content: center;justify-content: center;-webkit-align-items: center;align-items: center;">
				<image src="../../static/e1.jpg" mode="scaleToFill" style="height: 200rpx; width: 300rpx;"></image>
			</view>
			<view class="center-right uni-flex" style="-webkit-justify-content: center;justify-content: center;-webkit-align-items: center;align-items: center;">
				<view class="center-right-content uni-flex uni-column">
					<view class="center-right-content-top uni-flex uni-column" style="-webkit-justify-content: flex-start;justify-content: flex-start;">
						<text style="font-weight: 700; font-size: 30rpx;padding-bottom: 5rpx;">学历教育</text>
						<text class="center-right-content-top-text">为企业输送高质量人才</text>
						<text class="center-right-content-top-text">为企业输送高质量人才</text>
						<text class="center-right-content-top-text">为企业输送高质量人才</text>
					</view>
					<view @click="education" class="center-right-content-down uni-flex" style="-webkit-justify-content: flex-end;justify-content: flex-end;">
						<text style="color: red;">查看详情>></text>
					</view>
				</view>
			</view>
		</view>
		<view class="down" v-for="(n,index1) in ns" :key="index1">
			<view class="down_top uni-flex" style="-webkit-justify-content: center;justify-content: center;-webkit-align-items: center;align-items: center;">
				<text style="font-weight: 700; font-size: 30rpx;">{{n.name}}</text>
			</view>
			<view v-for="(imagsrc,index2) in imagesrcs" :key="index2" class="down_center uni-flex">
				<view class="down_center_left uni-flex uni-column" >
					<view class="down_center_left_top">
						<text style="font-weight: 700; font-size: 30rpx;">清华大学</text>
					</view>
					<view class="down_center_left_center">
						<text style="color: #464646;">学校位于五道口学校位于五道口学校位于五道口</text>
					</view>
					<view @click="academyopen(index2)" class="down_center_left_down" style="align-self: flex-end ;-webkit-align-self: flex-end ;">
						<text style="color: red;">查看更多>></text>
					</view>
				</view>
				<view class="down_center_right">
					<image :src="imagsrc.src" mode="scaleToFill" style="height: 160rpx; width: 220rpx;"></image>
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
				ns : [{
					name : '大学专利'
				},
				{
					name : '职校学历'
				}],
				imagesrcs :[{
					src : '../../static/e2.jpg'
				},
				{
					src : '../../static/e2.jpg'
				}]
			}
		},
		methods: {
			academyopen(e){
				switch (e){
					case 0:
						uni.navigateTo({
							url: '../academy/academy',
						});
						break;
					case 1:
						uni.navigateTo({
							url: '../history/history',
						});
						break;
					default:
						break;
				}
				
			},
			education(){
				uni.navigateTo({
					url: '../education/education',
				});
			}
		}
	}
</script>

<style>
	.swiper {
		height: 300rpx;
	}
	.swiper-item {
		height: 300rpx;
	}
	.center{
		height: 260rpx;
		width: 100%;
	}
	.center-left{
		width: 360rpx;
	}
	.center-right{
		padding-top: 30rpx;
	}
	.center-right-content{
		width: 340rpx;
	}
	.center-right-content-top{
		width: 340rpx;
	}
	.center-right-content-top-text{
		height: 30rpx;
		width: 296rpx;
		padding-bottom: 18rpx;
		color: #464646;
	}
	.down{
		padding-bottom: 10rpx;
		background-color: #ededed;
	}
	.down_top{
		height: 100rpx;
		background-color: #fff;
	}
	.down_center{
		background-color: #fff;
		border-bottom: #EDEDED 1rpx solid;
	}
	.down_center_left{
		width: 385rpx;
		padding-left: 55rpx;
	}
	.down_center_right{
		padding-left: 60rpx;
	}
</style>
