<template>
	<view>
		<view class="box1">
			fsdaf
		</view>
		<text class="text-color">外部引入样式</text>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	/* 引用外部 css */
	@import url("./style.css");
	.box1{
		width: 375rpx;
		height: 200rpx;
		font-size: 28rpx;
		background-color: #F0AD4E;
	}
</style>
