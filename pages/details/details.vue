<template>
	<view>
		<!-- 顶部图片自动切换 -->
		<view class="topimage">
			<image src="../../static/e4.jpg" mode="scaleToFill" style="height: 340rpx; width: 100%;"></image>
		</view>
		<!-- 标题的文字 -->
		<view class="down_title">
			<text style="font-weight: 700; font-size: 35rpx;">公司简介</text>
		</view>
		<!-- 循环输出内容与图片 -->
		<view class="down_center " v-for="(downcenter,index) in downcenters" :key="index">
			<!-- 文本 从数组中提取 -->
			<view class="down_center_text uni-flex uni-row" style="-webkit-justify-content: center;justify-content: center;">
				<text>{{downcenter.centertext}}</text>
			</view>
			<!-- 图片 从数组中提取 -->
			<view class="down_center_image">
				<image :src="downcenter.centerimage" mode="scaleToFill" style="height: 300rpx; width: 100%;"></image>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				downcenters : [{
					centertext : '在做企业咨询服务的这些日子里，发现一个有趣的现象在做企业咨询服务的这些日子里，发现一个有趣的现象在做企业咨询服务的这些日子里，发现一个有趣的现象在做企业咨询服务的这些日子里，发现一个有趣的现象在做企业咨询服务的这些日子里，发现一个有趣的现象在做企业咨询服务的这些日子里，发现一个有趣的现象，那就是各企业的都存在供需双方的矛盾，企业有人才需求，但是合适的人才都进不来，人才有需求，但是人才永远找不到合适的东家做搭档，这是人才要求高?我觉得这些都不是，而是各自对自身定位不准确的问题。企业希望人才全能但是合适的人才都进不来，人才有需求，但是人才永远找不到合适的东家做搭档:这是人才要求高个我觉得这些都不是，而是各',
					centerimage : '../../static/e5.jpg'
				},
				{
					centertext : '在做企业咨询服务的这些日子里，发现一个有趣的现象在做企业咨询服务的这些日子里，发现一个有趣的现象在做企业咨询服务的这些日子里，发现一个有趣的现象在做企业咨询服务的这些日子里，发现一个有趣的现象在做企业咨询服务的这些日子里，发现一个有趣的现象在做企业咨询服务的这些日子里，发现一个有趣的现象，那就是各企业的都存在供需双方的矛盾，企业有人才需求，但是合适的人才都进不来，人才有需求，但是人才永远找不到合适的东家做搭档，这是人才要求高?我觉得这些都不是，而是各自对自身定位不准确的问题。企业希望人才全能但是合适的人才都进不来，人才有需求，但是人才永远找不到合适的东家做搭档:这是人才要求高个我觉得这些都不是，而是各',
					centerimage : '../../static/e5.jpg'
				}]
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	.down_title{
		padding-left: 30rpx;
	}
	.down_center_text{
		/* width: 690rpx; */
		margin: 0 30rpx;
		height: 308rpx;
		line-height: 39rpx;
		overflow:hidden;
		text-overflow:ellipsis;
	}
	.down_center_image{
		height: 300rpx;
		padding: 30rpx 0;
	}
</style>
