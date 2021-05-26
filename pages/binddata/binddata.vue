<template>
	<view>
		<view class="title">
			<text>{{ title }}</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: "我是标题"
			}
		},
		methods: {
			
		}
	}
</script>

<style>
.title{
	font-size: 40rpx;
	font-weight: bold;
}
</style>
