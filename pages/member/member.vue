<template>
	<view>
		<view class="bg">
		    <!-- 头像 -->
		    <view class="head">
		    <view class="line"></view>
		    <view class="rq">
		              <view class="touxiang">
		            <open-data type="userAvatarUrl"></open-data>
		        </view>
		        <view class="nicheng">
		            <open-data type="userNickName" style="text-align: center;"></open-data>
		            <view style="color: #999;">
		                12456789@qq.com
		            </view>
		        </view>
		    </view> 
		</view>
		    <view class="count">
		     <view class="desc">
		        <view>23</view>
		        <view style="color: #999;">收藏</view>
		     </view>
		     <view class="desc">
		        <view>169</view>
		        <view style="color: #999;">关注</view>
		     </view>
		     <view class="desc">
		        <view>0</view>
		        <view style="color: #999;">动态</view>
		     </view>
		  </view>
		   
		  
		</view>
		  <!-- 签到 -->
		<view class="nav">
		  <view class="nav-1">
		      <view class="nav-item">
		         <image class="iconfont icon-qiandao" style="width:55rpx;height:50rpx"></image> 
		         <view>签到</view>
		      </view>
		      <view class="nav-item">
		        <image class="iconfont icon-jifen-xianxing" style="width:55rpx;height:50rpx"></image> 
		         <view>积分</view>
		      </view>
		      <view class="nav-item">
		        <image class="iconfont icon-renwuzhongxin_o" style="width:55rpx;height:50rpx"></image> 
		         <view>任务中心</view>
		      </view>
		  </view>
		</view>
		<view class="hr"></view>
		<!-- 设置 -->
		<view class="shezhi">
		     会员中心
		</view>
		<view class="hr"></view>
		
		
		
		<view class="sz">
		<!-- 会员中心 -->
		<view class="xx" style="border-bottom: 1rpx solid #f0f0f0;">
		   <view class="wz1">会员中心</view>
		   <view class="jt">
		      <text>></text>
		   </view>
		</view>
		<!-- 账号安全 -->
		<view class="xx" style="border-bottom: 1rpx solid #f0f0f0;">
		   <view class="wz1">红包卡券</view>
		   <view class="jt">
		      <text>点击领取优惠 ></text>
		   </view>
		</view>
		<view class="xx">
		   <view class="wz1">积分商城</view>
		   <view class="jt">
		      <text>></text>
		   </view>
		</view>
		</view>
		<view class="hr"></view>
		
		
		
		<!-- 设置 -->
		<view class="shezhi">
		     辅助功能
		</view>
		<view class="hr"></view>
		
		
		<view class="sz">
		<!-- 消息通知 -->
		<view class="xx" style="border-bottom: 1rpx solid #f0f0f0;">
		   <view class="wz1">消息通知</view>
		   <view class="jt">
		      <text>></text>
		   </view>
		</view>
		<!-- 关于我们 -->
		<view class="xx" style="border-bottom: 1rpx solid #f0f0f0;">
		   <view class="wz1">联系客服</view>
		   <view class="jt">
		      <text>></text>
		   </view>
		</view>
		<!-- 我的消费 -->
		<view class="xx" style="border-bottom: 1rpx solid #f0f0f0;">
		   <view class="wz1">版本更新</view>
		   <view class="jt">
		      <text>></text>
		   </view>
		</view>
		<view class="xx">
		   <view class="wz1">用户反馈</view>
		   <view class="jt">
		      <text>></text>
		   </view>
		</view>
		
		<view class="xx" bindtap="gopage">
		   <view class="wz1" >系统设置</view>
		   <view class="jt">
		      <text>></text>
		   </view>
		</view>
		
		</view>
		<!-- 退出 -->
		<view class="tc" bindtap="fanhui">
		   <view class="wz2">切换账号</view>
		   <view class="wz2">退出</view>
		</view>
		
		
		<view class="hr"></view>
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

<style lang="scss">
	.bg{
	    width: 100%;
	    height: 305rpx;
	    background-color: $shop-color;
	    color: white;
	    border-radius: 0 0 150rpx 150rpx;
	}
	.line{
	    height: 56rpx;
	    background-color: $shop-color;
	}
	.head{
	    height: 200rpx;
	    display: flex;
	    flex-direction: column;
	    align-items: center;
	}
	.rq{
	    width: 90%;
	    height: 166rpx;
	    display: flex;
	    flex-direction: column;
	    align-items: center;
	    background-color: #fff;
	    border-radius: 25rpx 25rpx 0 0;
	    border: 1rpx solid #f0f0f0;
	    /* border-bottom: 2rpx solid #ccc; */
	}
	.touxiang{
	    width: 100rpx;
	    height: 100rpx;
	    border-radius: 50%;
	    overflow: hidden;
	    box-shadow: 3rpx 3rpx 6rpx;
	    margin: -50rpx 0 5rpx 0;
	    border: 10rpx solid #fff;
	}
	.nicheng{
	    font-size: 27rpx;
	    display: flex;
	    flex-wrap: wrap;
	    flex-direction: column;
	    color: black;
	}
	/* 收藏 */
	.count{
	    width: 90%;
	    height: 97.9rpx;
	    display: flex;
	    margin: 0 auto;
	    background-color: #fff;
	    border-radius: 0 0 25rpx 25rpx;
	    border: 1rpx solid #f0f0f0;
	    box-shadow: 0 10rpx 5rpx #f0f0f0;
	}
	.desc{
	    flex: 1;
	    font-size: 28rpx;
	    line-height: 40rpx;
	    text-align: center;
	    margin-top: 6px;
	    color: #333;
	}
	/* 签到 */
	.nav{
	    height: 150rpx;
	    padding-top: 20rpx;
	    background-color: #fff;
	}
	.nav-1{
	    width: 90%;
	    height: 150rpx;
	    border-radius: 25rpx 25rpx 25rpx 25rpx;
	    background-color: #ffffff;
	    display: flex;
	    text-align: center;
	    margin: 0 auto;
	    border: 1rpx solid #f0f0f0;
	    box-shadow: 0 5rpx 5rpx #f0f0f0;
	}
	.nav-item{
	    flex: 1;
	    font-size: 24rpx;
	    margin-top: 25rpx;
	    margin-bottom: 20rpx;
	    color: #333;
	}
	.hr{
	    width: 100%;
	    height: 20rpx;
	}
	/* 设置 */
	.sz{
	    width: 90%;
	    display: flex;
	    flex-direction: column;
	    margin: 0 auto;
	    border: 1rpx solid #f0f0f0;
	    border-radius: 25rpx 25rpx 25rpx 25rpx;
	    box-shadow: 0 5rpx 5rpx #f0f0f0;
	}
	.shezhi{
	    padding-top: 5rpx;
	    color: #999;
	    font-size: 24rpx;
	    padding-left: 70rpx;
	}
	.xx{
	    display: flex;
	}
	.wz1{
	    font-size: 28rpx;
	    padding-top: 30rpx;
	    padding-bottom: 30rpx;
	    padding-left: 30rpx;
	}
	.jt{
	    font-size: 28rpx;
	    position: absolute;
	    right: 50rpx;
	    height: 100rpx;
	    line-height: 100rpx;
	    color: #888;
	}
	.tc{
	    height: 200rpx;
	}
	.wz2{
	    color: $shop-color;
	    display: flex;
	    justify-content: center;
	    margin-top: 40rpx;
	}
</style>
