<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
		
		<button type="primary" @click="getData">发送网络请求</button>
		<button type="primary" @click="uploadImg">上传图片</button>
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
			},
			uploadImg() {
				uni.chooseImage({
				    count: 6,
				    success: function(res) {
				        // 预览图片
								console.log(res)
								uni.previewImage({
								            urls: res.tempFilePaths,
								            longPressActions: {
								                itemList: ['发送给朋友', '保存图片', '收藏'],
								                success: function(data) {
								                    console.log('选中了第' + (data.tapIndex + 1) + '个按钮,第' + (data.index + 1) + '张图片');
								                },
								                fail: function(err) {
								                    console.log(err.errMsg);
								                }
								            }
								        });
				    }
				    });
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
