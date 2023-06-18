<template>
	<view>
		<view class="main container">
		    <view class="cart">
		        <view class="cart_con">
		            <view class="cartcon_list">
		                <ul>
		                    <li class="clearfloat">
		                        <span>
									<label>
										<checkbox type="checkbox" class="cart_checkbox" @click="alp == false"></checkbox>
									</label>
									
								</span>
								<view style="width: 180rpx;">
									<a href="" class="cart_img" style="width: 150rpx;height: 100rpx;"><image src="../../static/素材/heima_shop_server/src/public/upload/201504/16/7.jpg"></image> </a>
									<a href="" class="cart_title">商品1号</a>
								</view>
		                       
		                        <view style="width: 150rpx;">
		                            <span>-</span><input type="text" value="2"><span>+</span>
		                        </view>
		                        <strong>¥910,599.00</strong>
		                        <em style="margin-right: 50rpx;"></em>
		                    </li>
		                    <li class="clearfloat">
		                        <span>
		                        	<label>
		                        		<checkbox type="checkbox" class="cart_checkbox" @click="alp == false"></checkbox>
		                        	</label>
		                        	
		                        </span>
								<view style="width: 180rpx;">
									<a href="" class="cart_img" style="width: 150rpx;height: 100rpx;"><image src="../../static/素材/heima_shop_server/src/public/upload/201504/16/3.jpg" mode=""></image> </a>
									<a href="" class="cart_title">商品2号</a>
								</view>
		                        
		                        <view style="width: 150rpx;">
		                            <span>-</span><input type="text" value="2"><span>+</span>
		                        </view>
		                        <strong>¥915,990.00</strong>
		                        <em style="margin-right: 50rpx;"></em>
		                    </li>
		                </ul>
		            </view>
		        </view>
		        <view class="cart_header">
					<span>商品总数<em>2</em>件</span>
		           
		            <span>￥：<strong>1,826,589.00</strong></span>
		            <button type="button" style="line-height: 35px;margin-right: 10px;">结算</button>
		        </view>
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
			alp(){
				this.alp = !this.alp
			}
		}
	}
</script>

<style lang="scss">
	ul {
	    list-style: none;
		padding: 0;
		margin: 0;
	}
	a{
	    color:#555;
	    text-decoration: none;
	}
	a:hover {
	    color:#f30;
	    text-decoration: none;
	}
	.container {
	    width: 100%;
	    margin: 0 auto;
	}
	.cart {
	    margin-top:20px;
	}
	.cart_header {
	    text-align: right;
	    font-size: 28rpx;
	    line-height: 72rpx;
	}
	.cart_header>button{
	    display: inline-block;
	    vertical-align: middle;
	    width: 200rpx;
	    height: 72rpx;
	    background: #f63;
	    border:none;
	    color:#fff;
	    font-size: 36rpx;
	}
	.cart_header>span {
	    margin-right: 10px;
	    display: inline-block;
	    vertical-align: middle;
	}
	.cart_header>span>em {
	    font-style: normal;
	    color:#f63;
	}
	.cart_header>span>strong{
	    font-size: 36rpx;
	    color:#f63;
	}
	.cart_header>p {
	    float: left;
	    width: 100%;
	    text-align: center;
	}
	.cart_con {
	    margin: 10px 0;
	    font-size: 28rpx;
	}
	/*购物车列表*/
	.cartcon_list h2 {
	    line-height: 120rpx;
	    text-align: center;
	    font-size: 36rpx;
	    font-weight: lighter;
	    border: 1px solid #ddd;
	    border-top: none;
	}
	.cartcon_list h2 a {
	    color:#f60;
	}
	.cartcon_list ul li {
	    padding: 10px 0;
	    border: 1px solid #ddd;
	    border-top: none;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
	.cartcon_list>ul>li>span,
	.cartcon_list>ul>li>a,
	.cartcon_list>ul>li>i,
	.cartcon_list>ul>li>view,
	.cartcon_list>ul>li>view>span,
	.cartcon_list>ul>li>view>input,
	.cartcon_list>ul>li>strong,
	.cartcon_list>ul>li>em {
	    display: inline-block;
	    vertical-align: middle;
	    text-align: center;
	    font-style: normal;
	}
	.cartcon_list>ul>li>span {
	    width: 60rpx;
	}
	.cart_img {
		display: block;
	    overflow: hidden;
		margin-top: 20rpx;
	}
	.cart_img image{
	    width: 100%;
	    height: 100%;
	}
	.cart_title {
	    width: 180rpx;
	    font-size: 18rpx;
		margin-top: 10rpx;
	    text-align: left;
		display: block;
	}
	.cartcon_list>ul>li>i {
	    width: 200rpx;
	}
	.cartcon_list>ul>li>view {
	    width: 240rpx;
	}
	.cartcon_list>ul>li>view>span {
	    width: 40rpx;
	    height: 40rpx;
	    background: #e8e8e8;
	    line-height: 40rpx;
	}
	.cartcon_list>ul>li>view>span:hover {
	    cursor: pointer;
	    background: #eee;
	}
	.cartcon_list>ul>li>view>input {
	    width: 56rpx;
	    height: 36rpx;
	    border:1px solid #ccc;
	}
	.cartcon_list>ul>li>strong {
	    width: 200rpx;
	    color:#f63;
	}
	.cartcon_list>ul>li>em {
	    margin-left: 20px;
	    width: 28rpx;
	    height: 28rpx;
	    background:url(../../static/iconlist.png) no-repeat 0 -920rpx;
	    cursor: pointer;
	}
	.cartcon_list>ul>li>em:hover {
	    background-position: 0 -920rpx;
	}
	.cart_checkbox{
		margin-left: 10rpx;
	}
</style>
