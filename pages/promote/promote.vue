<template>
	<view>
		<!-- 顶部图片轮换 -->
		<view class="top">
			<swiper class="swiper" circular :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
				<swiper-item>
					<view class="swiper-item">
						<image src="../../static/EliteEducation.jpg" mode="scaleToFill" style="height: 300rpx; width: 100%;"></image>
					</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item">
						<image src="../../static/EliteEducation.jpg" mode="scaleToFill" style="height: 300rpx; width: 100%;"></image>
					</view>
				</swiper-item>
			</swiper>
		</view>
		<!-- 中间学历教育模块 -->
		<view class="center uni-flex uni-row">
			<!-- 图片 -->
			<view class="center-left uni-flex" style="-webkit-justify-content: center;justify-content: center;-webkit-align-items: center;align-items: center;">
				<image src="../../static/e1.jpg" mode="scaleToFill" style="height: 200rpx; width: 300rpx;"></image>
			</view>
			<!-- 文本内容 -->
			<view class="center-right uni-flex" style="-webkit-justify-content: center;justify-content: center;-webkit-align-items: center;align-items: center;">
				<view class="center-right-content uni-flex uni-column">
					<!-- 文本内容 -->
					<view class="center-right-content-top uni-flex uni-column" style="-webkit-justify-content: flex-start;justify-content: flex-start;">
						<text style="font-weight: 700; font-size: 35rpx;padding-bottom: 5rpx;">学历教育</text>
						<text class="center-right-content-top-text">为企业输送高质量人才</text>
						<text class="center-right-content-top-text">为企业输送高质量人才</text>
						<text class="center-right-content-top-text">为企业输送高质量人才</text>
					</view>
					<!-- 页面跳转 -->
					<view @click="education" class="center-right-content-down uni-flex" style="-webkit-justify-content: flex-end;justify-content: flex-end;">
						<text style="color: red;">查看详情>></text>
					</view>
				</view>
			</view>
		</view>
		<!-- 底部内容循环输出 -->
		<view class="down" v-for="(title,index1) in titles" :key="index1">
			<!-- 标题 -->
			<view class="down_top uni-flex" style="-webkit-justify-content: center;justify-content: center;-webkit-align-items: center;align-items: center;">
				<text style="font-weight: 700; font-size: 35rpx;">{{title.name}}</text>
			</view>
			<!-- 模块内的循环输出 -->
			<view v-for="(submodule,index2) in submodules" :key="index2" class="down_center uni-flex">
				<view class="down_center_left uni-flex uni-column" >
					<!-- 文本内容 -->
					<view class="down_center_left_top">
						<text style="font-weight: 700; font-size: 35rpx;">{{submodule.titletext}}</text>
					</view>
					<view class="down_center_left_center">
						<text style="color: #666;">{{submodule.contenttext}}</text>
					</view>
					<!-- 跳转界面 -->
					<view @click="academyopen(index2)" class="down_center_left_down" style="align-self: flex-end ;-webkit-align-self: flex-end ;">
						<text style="color: red;">查看更多>></text>
					</view>
				</view>
				<!-- 图片 -->
				<view class="down_center_right">
					<image :src="submodule.src" mode="scaleToFill" style="height: 160rpx; width: 220rpx;"></image>
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
				titles : [{
					name : '大学专利'
				},
				{
					name : '职校学历'
				}],
				submodules :[{
					titletext : '清华大学',
					contenttext : '学校位于五道口学校位于五道口学校位于五道口',
					src : '../../static/e2.jpg',
					url : '../academy/academy'
				},
				{
					titletext : '清xx学',
					contenttext : '学校位于五道口学校位于五道口学校位于五道口',
					src : '../../static/e2.jpg',
					url : '../history/history'
				}]
			}
		},
		methods: {
			academyopen(e){
				uni.navigateTo({
					url: this.submodules[e].url
				});
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
		color: #666;
		overflow:hidden;
		text-overflow:ellipsis;
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
