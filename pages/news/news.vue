<template>
	<view class="news">
		<news-item @itemClick="goDetail" :list="newsList"></news-item>
	</view>
</template>

<script>
	import newsList from '../../components/news-item/news-item.vue'
	export default {
		data() {
			return {
				newsList:[]
			}
		},
		methods: {
			async getNews(){
				const res = await this.$myRuquest({
					url:'/api/getnewslist'
				})
				this.newsList = res.data.message
				console.log(res)
			},
			goDetail(id){
				uni.navigateTo({
					url:'/pages/news-detail/news-detail?id='+id
				})
			}
		},
		components: {"news-item":newsList},
		onLoad(){
			this.getNews()
		}
	}
</script>

<style lang="scss">
	.news{
		
	}
</style>
