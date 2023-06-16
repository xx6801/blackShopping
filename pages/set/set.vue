<template>
	<view>
		<view class="item">
		   <view class="title">编辑资料</view>
		   <view class="detail2">
		    <view class="touxiang">
		            <image src="../../static/素材/hmlogo.png" style="width: 100%;height: 100%;"></image>
		        </view>
		   </view>
		</view>
		<view class="hr1">安全</view>
		<view class="item">
		   <view class="title">账号管理</view>
		   <view class="detail2">
		      <text>></text>
		   </view>
		</view>
		<view class="hr"></view>
		<view class="item">
		   <view class="title">手机号码</view>
		   <view class="detail2">
		      <text>189******80  ></text>
		   </view>
		</view>
		<view class="hr"></view>
		<view class="item">
		   <view class="title">账号与安全</view>
		   <view class="detail2">
		      <text>></text>
		   </view>
		</view>
		<view class="hr1">通用</view>
		<view class="item">
		   <view class="title">内容举报</view>
		   <view class="detail2">
		      <text>></text>
		   </view>
		</view>
		<view class="hr1">隐私</view>
		<view class="item">
		   <view class="title">我的收藏</view>
		   <view class="detail2">
		      <text>开放 ></text>
		   </view>
		</view>
		<view class="hr"></view>
		<view class="item">
		   <view class="title">我的下载</view>
		   <view class="detail2">
		      <text>私密 ></text>
		   </view>
		</view>
		<view class="hr"></view>
		<view class="item">
		   <view class="title">清除缓存</view>
		   <view class="detail2">
		      <text>402.80MB</text>
		   </view>
		</view>
		<view class="hr2"></view>
		<view class="item">
		   <view class="title">关于我们</view>
		   <view class="detail2">
		      <text>></text>
		   </view>
		</view>
		<view class="hr"></view>
		<view class="item">
		   <view class="title">帮助中心</view>
		   <view class="detail2">
		      <text>></text>
		   </view>
		</view>
		<view class="hr"></view>
		<view class="item">
		   <view class="title">账户注销</view>
		   <view class="detail2">
		      <text>></text>
		   </view>
		</view>
		<view class="hr"></view>
		
		<button class="tc" @click="goLoginClick" style="color: #d53c3e;">退出</button>
		<view class="line"></view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			goLoginClick(id){
				uni.navigateTo({
					url:'/pages/login/login?id='+id
				})
			}
		}
	}
</script>

<style lang="scss">
	.touxiang{
	    width: 66rpx;
	    height: 66rpx;
	    border-radius: 50%;
	    overflow: hidden;
	    box-shadow: 3rpx 3rpx 6rpx;
	    margin-left: 40rpx;
	    margin-top: 20rpx;
	}
	.item{
	    display: flex;
	}
	.title{
	    font-size: 28rpx;
	    padding-top: 30rpx;
	    padding-bottom: 30rpx;
	    padding-left: 30rpx;
	}
	.detail2{
	    font-size: 28rpx;
	    position: absolute;
	    right: 20rpx;
	    height: 100rpx;
	    line-height: 100rpx;
	    color: #888;
	}
	.hr{
	    width: 100%;
	    height: 2rpx;
	    background-color: #f0f0f0;
	}
	.hr1{
	    width: 100%;
	    height: 60rpx;
	    font-size: 24rpx;
	    color: #999;
	    line-height: 60rpx;
	    padding-left: 30rpx;
	    background-color: #f0f0f0;
	}
	.hr2{
	    width: 100%;
	    height: 30rpx;
	    background-color: #f0f0f0;
	}
	.tc{
	    width: 200rpx;
	    height: 60rpx;
	    line-height: 60rpx;
	    margin-top: 50rpx;
	    font-size: 28rpx;
	    font-weight: bold;
	}
	.line{
	    width: 100%;
	    height: 50rpx;
	    background-color: #ffffff;
	}
</style>
