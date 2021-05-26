<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
		
		<button type="primary" @click="getData">发送网络请求</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				num: 30
			}
		},
		
		onInit() {
				console.log("index onInit")
		},
		onLoad(options) {
			console.log("index onLoad")
		},
		onShow() {
			console.log("index show")
		},
		onHide() {
			console.log("index onHide")
		},
		onReady() {
			console.log("index onReady")
		},
		onUnload() {
			console.log("index onUnload")
		},
		onPullDownRefresh() {
			console.log("下拉刷新")
			setTimeout(function(){
				uni.stopPullDownRefresh()
			}, 2000)
		},
		onReachBottom() {
			this.num += 20
		},
		methods: {
			pullDown() {
				uni.startPullDownRefresh()
			},
			getData() {
				uni.request({
				    url: '', //仅为示例，并非真实接口地址。
				    method: "GET",
				    success: (res) => {
				        console.log(res.data);
				        this.text = 'request success';
				    }
				})
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
