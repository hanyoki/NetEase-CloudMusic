<template name="Header">
	<view>
		<view class="status-bar"></view>
		<view class="header">
			<view class="header-menu-icon">
				<text class="text-black cuIcon-sort" @tap="showDrawer"></text>
			</view>
			<view class="header-menu">
				<view :class="current==0?'selected':''" @tap="childChangeView(0)">
					我的
				</view>
				<view :class="current==1?'selected':''" @tap="childChangeView(1)">
					发现
				</view>
				<view :class="current==2?'selected':''" @tap="childChangeView(2)">
					云村
				</view>
				<view :class="current==3?'selected':''" @tap="childChangeView(3)">
					视频
				</view>
			</view>
			<view class="header-search-icon">
				<text class="text-black cuIcon-search" @tap="goSearch"></text>
			</view>
		</view>		
	</view>
</template>

<script>
	export default {
		name: "Header",
		props:{
			current:{
				type: Number,
				default: 1
			}
		},
		data() {
			return{
				
			}
		},
		methods:{
			childChangeView(id){
				this.$emit('changeView', id);
			},
			goSearch(){
				uni.navigateTo({
					url: '../../pages/search/search'
				})
			},
			showDrawer(){
				this.$emit('showDrawer', true);
			}
		}
	}
</script>

<style>
	@import url("./index.css");
</style>
