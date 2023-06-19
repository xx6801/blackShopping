<template>
	<view>
		<view class="content">
		    <view class="cart" v-for="(item,idx) in list">
				<u-checkbox-group>
					<u-checkbox @change="item.checked = !item.checked" :checked="item.checked"></u-checkbox>
				</u-checkbox-group>
				<image :src="item.img" @longtap="del(idx)"></image>
				<view @longtap="del(idx)">
					<view>{{item.name}}</view>
					<view>单价：￥{{Fix(item.price)}}</view>
					<view>小计：￥{{Fix(item.price * item.qty)}}</view>
				</view>
				<u-number-box v-model="item.qty"></u-number-box>	
		    </view>
			合计：￥{{Fix(total)}}
			<u-button text="结算" type="warning"></u-button>
		</view>
	</view>
</template>

<script>
	function product(name,img,price,qty,checked){
		this.name = name;
		this.img = img ? img : "../../static/hmlogo.png";
		this.price = price;
		this.qty = qty ? qty : 1;
		this.checked = checked != null ? checked : true;//商品是否选中状态
	}
	export default {
		data() {
			return {
				list:[
					new product("豪华餐桌1","../../static/hmlogo.png",27.8),
					new product("豪华餐桌2","../../static/hmlogo.png",66.6,2),
					new product("豪华餐桌3","../../static/hmlogo.png",2.99,5),
					new product("豪华餐桌4","../../static/hmlogo.png",25.2),
					new product("豪华餐桌4","../../static/hmlogo.png",87.8)
				]
			}
		},
		computed:{
			total(){
				var sum = 0;
				for(var i in this.list){
					var item = this.list[i];
					if(item.checked) //如果选中才进行累加
					sum += item.qty * item.price;
				}
				return sum;
			}
		},
		onLoad(){
			
		},
		methods: {
			Fix(v){
				return v.toFixed(2);
			},
			del(idx){
				// this.list.splice(idx,1);
				var item = this.list[idx];
				uni.showModal({
					title: `确认删除 ${item.name} 吗？`
				}).then((rs) =>{
					console.log(rs);
					if(rs.confirm || (rs[1] && rs[1].confirm) ){
						this.list.splice(idx,1);
					}
				});

			}
		}
	}
</script>

<style lang="scss">
	.cart {
	    display: flex;
		margin: 10rpx;
		padding: 10rpx;
		border-bottom: solid 1px #ddd;
		align-items: center;
		image{
			margin: 0 10rpx;
			width: 180rpx;
			height: 180rpx;
		}
		view:nth-child(3){  //中间的文字部分
			display: flex;
			flex-direction: column;
			flex: 1;
			view:nth-child(2){   //单价
				flex: 1;
				display: flex;
				align-items: center;
			}
			view:last-child{  //小计
				color: orangered;
			}
		}
	}
</style>
