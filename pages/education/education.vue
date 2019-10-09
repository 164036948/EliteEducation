<template>
	<view>
		<!-- 顶部标题文字 -->
		<view class="title uni-flex" style="height: 90rpx;-webkit-justify-content: center;justify-content: center;-webkit-align-items: center;align-items: center;">
			<text>学历教育</text>
		</view>
		<!-- 主要内容包括图片和文本使用循环输出 -->
		<view v-for="(imagesrc,index) in imagesrcs" :key="index" class="center uni-flex uni-column" style="-webkit-justify-content: center;justify-content: center;-webkit-align-items: center;align-items: center;">
			<!-- 图片地址使用数组 -->
			<view class="center_image uni-flex" style="padding-bottom: 35rpx;height: 300rpx;-webkit-justify-content: center;justify-content: center;-webkit-align-items: center;align-items: center;">
				<image :src="imagesrc.src" mode="scaleToFill" style="height: 300rpx; width: 600rpx;"></image>
			</view>
			<!-- 文本 -->
			<view class="center_text ">
				<text>在做企业咨询服务的这些日子里,发现个有趣的现象,那就是各企业的都存在供需双方的矛盾,企业有人才需求,但是合适的人才都进不来,人才有需求,但是人才永远找不到合适的东家做搭档;这是人才要求高?我觉得这些都不是,而是各自对自身定位不准确的问题。企业希望人才全能...</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				imagesrcs :[{
					src : '../../static/e3.jpg'
				},
				{
					src : '../../static/e3.jpg'
				}]
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	.center{
		height: 520rpx;
		padding-bottom: 40rpx;
	}
	.center_text{
		 width: 675rpx;
		 height: 184rpx;
		 color: #666;
		 line-height: 38rpx;
		 overflow:hidden;
		 text-overflow:ellipsis;
	}
</style>
