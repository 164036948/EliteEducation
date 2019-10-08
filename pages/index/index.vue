<template>
	<view class="content uni-flex uni-column">
		<view class="mid uni-flex uni-row" style="-webkit-flex: 1;flex: 1;">
			123
		</view>
		<view class="tabbar uni-flex uni-row ">
			<view class="tabbar_one" style="width: 100rpx;">
				
			</view>
			<view class="tabbar_two uni-flex" style="flex-grow:1;-webkit-justify-content: center;justify-content: center;-webkit-align-items: center;align-items: center;">
				<text>我的</text>
			</view>
			<view class="tabbar_three uni-flex" style="flex-grow:1;-webkit-justify-content: center;justify-content: center;-webkit-align-items: center;align-items: center;"
			@click="openElevate">
				<text>学历提升</text>
			</view>
			<view class="tabbar_four uni-flex" style="flex-grow:1;-webkit-justify-content: center;justify-content: center;-webkit-align-items: center;align-items: center;"
			@click="openIntro">
				<text>公司简介</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
			}
		},
		onLoad() {

		},
		methods: {
			openElevate(){
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
	.content{
		height: 100vh;
	}
	.mid{
		background-color: #ededed;
		border-top: #d2d2d2 1rpx solid;
	}
	.tabbar{
		height: 100rpx;
	}
</style>
