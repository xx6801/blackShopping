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
			<view style="width: 100%; height: 20px;"></view>
			合计：
			<span class="heji">
				￥{{Fix(total)}}
			</span>
			<view style="width: 100%; height: 20px;"></view>
			
			<u-button text="结算" type="warning" style="width: 90%;"></u-button>
			<view style="width: 100%; height: 20px;"></view>
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
					new product("华为（HUAWEI）荣耀6Plus 16G双4G版","http://localhost:8082/upload/201504/20/thumb_201504200119256512.jpg",2195),
					new product("小米（Mi）小米Note 16G双网通版","http://localhost:8082/upload/201504/20/thumb_201504200119256514.jpg",2199,2),
					new product("尼康(Nikon)D3300套机（18-55mm f/3.5-5.6G VRII）（黑色）","http://localhost:8082/upload/201504/20/thumb_201504200119256515.jpg",4799,5),
					new product("金士顿（Kingston） DataTraveler SE9 32GB 金属U盘","http://localhost:8082/upload/201504/20/thumb_201504200119256519.jpg",79),
					new product("惠普(HP) Officejet Pro 8610商用彩色喷墨一体机","http://localhost:8082/upload/201504/20/thumb_201504200119256521.jpg",1999)
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
			font-size: 12px;
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
	.heji{
		color: $shop-color;
	}
</style>
