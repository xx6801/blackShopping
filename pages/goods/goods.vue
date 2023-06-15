<template>
	<view class="goods_list">
		<goods-list @goodsItemClick="goGoodsDetail" :goods="goods"></goods-list>
		<view class="isDver" v-if="flag">-----我是有底线的-----</view>
	</view>
</template>

<script>
	import goodsList from '../../components/goods-list/goods-list.vue'
	export default {
		data() {
			return {
				pageindex:1,
				goods:[],
				flag:false
			}
		},
		components:{"goods-list":goodsList},
		methods: {
			//获取商品列表的数据
			async getGoodsList(callBack){
				const res =await this.$myRuquest({
					url:'/api/getgoods?pageindex='+this.pageindex
				})
				this.goods = [...this.goods,...res.data.message]
				console.log(res)
				callBack && callBack()
			},
			//导航到商品详情页
			goGoodsDetail(id){
				uni.navigateTo({
					url:'/pages/goods-detail/goods-detail?id='+id
				})
			}
		},
		onLoad(){
			this.getGoodsList()
		},
		onReachBottom(){
			if(this.goods.length<this.pageindex*10) return this.flag = true
			console.log('10')
			this.pageindex++
			this.getGoodsList()
		},
		onPullDownRefresh(){
			console.log('ooo')
			this.pageindex = 1
			this.goods = []
			this.flag = false
			setTimeout(()=>{
			this.getGoodsList(()=>{
				uni.stopPullDownRefresh()
			})	
			},1000)
			
		}
	}
</script>

<style lang="scss">
	.goods_list{
		background: #eee;
	}
	.isDver{
		width: 100%;
		height: 50px;
		line-height: 50px;
		text-align: center;
		font-size: 28rpx;
		color: #999;
	}
</style>
