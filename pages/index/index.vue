<template>
	<view class="content uni-flex uni-column" :style="{height:windowHeight }">
		<!-- 中间填充屏幕 -->
		<view class="mid uni-flex uni-row" style="-webkit-flex: 1;flex: 1;">
			
		</view>
		<!-- 点击我的显示再次点击隐藏 -->
		<cover-view v-show="see" class="cover-view1" :style="{top:top1 }">求职</cover-view>
		<cover-view v-show="see" class="cover-view2" :style="{top:top2 }">招聘</cover-view>
		<!-- 底部导航栏 -->
		<view class="tabbar uni-flex uni-row ">
			<!-- 键盘图位置 -->
			<view class="tabbar_one" style="width: 99rpx;border-right: #e5e5e5 1rpx solid;" >
				<image src="../../static/e7.jpg" mode="scaleToFill" style="height: 90rpx; width: 100rpx;"></image>
			</view>
			<!-- 我的标签位置 -->
			<view @click="altersee" class="tabbar_two uni-flex" style="width: 216rpx;border-right: #e5e5e5 1rpx solid;-webkit-justify-content: center;justify-content: center;-webkit-align-items: center;align-items: center;">
				<image src="../../static/e6.jpg" mode="scaleToFill" style="height: 30rpx; width: 30rpx;"></image>
				<text>我的</text>
			</view>
			<!-- 学历提升标签位置 -->
			<view class="tabbar_three uni-flex" style="width: 216rpx;border-right: #e5e5e5 1rpx solid;-webkit-justify-content: center;justify-content: center;-webkit-align-items: center;align-items: center;"
			@click="openPromote">
				<image src="../../static/e6.jpg" mode="scaleToFill" style="height: 30rpx; width: 30rpx;"></image>
				<text>学历提升</text>
			</view>
			<!-- 公司简介标签位置 -->
			<view class="tabbar_four uni-flex" style="width: 216rpx;-webkit-justify-content: center;justify-content: center;-webkit-align-items: center;align-items: center;"
			@click="openIntro">
				<image src="../../static/e6.jpg" mode="scaleToFill" style="height: 30rpx; width: 30rpx;"></image>
				<text>公司简介</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				top1 : '',
				top2 : '',
				see : false,
				windowHeight : ''
			}
		},
		onReady(){
			uni.getSystemInfo({
				success: res =>  {
					this.top1=750*res.windowHeight/res.windowWidth-100-84-84+"rpx";
					this.top2=750*res.windowHeight/res.windowWidth-100-84+"rpx";
					this.windowHeight=750*res.windowHeight/res.windowWidth+"rpx";
					// console.log(this.windowHeight);
				}
			})
			
		},
		methods: {
			altersee(){
				if(this.see==false){
					this.see=true
				}else{
					this.see=false
				}
			},
			openPromote(){
				uni.navigateTo({
					url: '../promote/promote'
				});
			},
			openIntro(){
				uni.navigateTo({
					url: '../intro/intro'
				});
			}

		}
	}
</script>

<style>
	.mid{
		background-color: #ededed;
		border-top: #d2d2d2 1rpx solid;
	}
	.tabbar{
		height: 100rpx;
	}
	.cover-view1,.cover-view2 {
		position: absolute;
		left: 101rpx;
		width: 217rpx;
		height: 85rpx;
		line-height: 85rpx;
		text-align: center;
	}
	.cover-view1{
		background-color: #f8f8f8;
	}
	.cover-view2{
		background-color: #aeaeae;
	}
</style>
