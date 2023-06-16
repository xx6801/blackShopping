<template>
	<view>
		<view class="bg">
		<view class="line">
		    
		</view>
		  <view class="touxiang">
		    <image src="../../static/素材/hmlogo.png" style="width: 100%;height: 100%;"></image>
		  </view>
		  <view class="nicheng">
		    <text style="text-align: center;">黑马</text>
		  </view>
		  <view class="hm">
		      189****6251
		  </view>
		  <view>
		    <button class="dl" @click="goIndexClick">一键登录</button>
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
		methods: {
			goIndexClick(id){
				uni.switchTab({
					url:'/pages/index/index?id='+id
				})
			}
		}
	}
</script>

<style lang="scss">
	.bg{
	    width: 100%;
	    height: 1500rpx;
	    background-size: 100%;
	    background-repeat: no-repeat;
		
	}
	.touxiang{
	    width: 120rpx;
	    height: 120rpx;
	    overflow: hidden;
	    border-radius: 50%;
	    margin: 200rpx auto 0;
	}
	.nicheng{
	    margin-top: 20rpx;
	    font-size: 30rpx;
	    text-align: center;
	}
	.hm{
	    margin-top: 10rpx;
	    text-align: center;
	    font-weight: bold;
	}
	.dl{
	    width: 80%;
	    background-color: $shop-color;
	    color: #fff;
	    margin-top: 40rpx;
	    font-size: 34rpx;
	}
	
	.line{
	    width: 100%;
	    height: 300rpx;
	}
</style>
