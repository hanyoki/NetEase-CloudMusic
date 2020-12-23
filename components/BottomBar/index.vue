<template name="BottomBar">
	<view class="bottom">
		<view class="bottom-left">
			<image src="../../static/images/videodisc.png" mode="" @tap="goPlay"></image>
			<view class="aideo-info" @tap="goPlay">
				<view class="audio-name">
					黄昏
				</view>
				<view class="audio-singer">
					周传雄
				</view>
			</view>
		</view>
		<view class="bottom-right">
			<view class="btn-player">
				<text class="text-black cuIcon-playfill" @tap="goPlay"></text>
			</view>
			<view class="btn-info">
				<text class="text-black cuIcon-list"></text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name: "BottomBar",
		props:{},
		data() {
			return{
				
			}
		},
		methods:{
			goPlay(){
				uni.navigateTo({
					url: '../../pages/play/play'
				})
			}
		}
	}
</script>

<style>
	@import url("./index.css");
</style>
