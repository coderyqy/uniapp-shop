<template>
	<view>
		<view class="title">
			<text>{{ title }}</text>
		</view>
		<view v-for="(item, index) in infoList" :key="index">
			{{item.name}}
		</view>
		<button type="default" @click="clickHandle(20, $event)">按钮</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: "我是标题",
				infoList: [
					{
						name: '张三'
					},
					{
						name: '张三老爸'
					},
					{
						name: '张三爷爷'
					},
					{
						name: '我是大佬'
					}
				]
			}
		},
		methods: {
			clickHandle(num, e) {
				console.log("唐伯虎点秋香")
				console.log(num)
				console.log(e)
			}
		}
	}
</script>

<style>
.title{
	font-size: 40rpx;
	font-weight: bold;
}
</style>
