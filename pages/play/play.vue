<template>
	<view class="content">
		<view class="status-bar"></view>
		<!-- header -->
		<view class="player-header">
			<text class="player-header-icon text-white cuIcon-back" @tap="goBack"></text>
			<view class="player-header-title">
				<view class="title-name">
					黄昏
				</view>
				<view class="title-msg">
					周传雄
				</view>
			</view>
			<text class="player-header-share text-white cuIcon-share"></text>
		</view>
		<!-- videodisc -->
		<view class="player-videodisc">
			<image src="../../static/images/videodisc.png" mode=""></image>
		</view>
		<!-- optBar -->
		<view class="play-opt-bar">
			<view class="" v-for="(item, index) in optList" :key="index">
				<text class="text-white" :class="item.icon"></text>
			</view>

		</view>
		<!-- slider -->
		<view class="player-slider">
			<view class="player-currentTime">
				{{chCurrentTime[0]}}:{{chCurrentTime[1]}}
			</view>
			<slider 
			class="slider"
			min="0"
			:max="duration"
			:value="currentTime"
			activeColor="#b6b6b6"
			backgroundColor="#dedede"
			block-size="12"
			@change="changeProgress"
			/>
			<view class="player-duration">
				{{chDuration[0]}}:{{chDuration[1]}}
			</view>
		</view>
		<!-- playbar -->
		<view class="play-bar">
			<view class="">
				<text class="text-white cuIcon-repeal"></text>
			</view>
			<view class="">
				<text class="text-white cuIcon-backwardfill"></text>
			</view>
			<view class="play-menu">
				<text class="text-white cuIcon-playfill" :class="ifPlay?'cuIcon-stop':'cuIcon-playfill'" @tap="playMusic"></text>
			</view>
			<view class="">
				<text class="text-white cuIcon-play_forward_fill"></text>
			</view>
			<view class="">
				<text class="text-white cuIcon-list"></text>
			</view>
			
		</view>
	</view>
</template>

<script>
	const audioContext = uni.createInnerAudioContext();
	audioContext.autoplay = false;
	audioContext.src = 'http://music.163.com/song/media/outer/url?id=190072.mp3';
	export default {
		data() {
			return {
				optList:[{
						'id': 0,
						'icon': 'cuIcon-like'
					},{
						'id': 1,
						'icon': 'cuIcon-down'
					},{
						'id': 2,
						'icon': 'cuIcon-notice'
					},{
						'id': 3,
						'icon': 'cuIcon-message'
					},{
						'id': 4,
						'icon': 'cuIcon-moreandroid'
					},
				],
				duration: '100',
				currentTime: '0',
				chDuration: ['0', '00'],
				chCurrentTime: ['0', '00'],
				ifPlay: false,
			}
		},
		methods: {
			goBack(){
				history.back();
			},
			playMusic(){
				var duration = audioContext.duration;
				var currentTime = audioContext.currentTime;
				this.duration = duration;
				this.currentTime = currentTime;
				this.chDuration[0] = Math.floor(Math.floor(duration)/60);
				this.chDuration[1] = Math.floor(duration)%60;
				this.chCurrentTime[0] = Math.floor(Math.floor(currentTime)/60);
				this.chCurrentTime[1] = Math.floor(currentTime)%60;
				if (this.ifPlay) {
					this.ifPlay = false;
					audioContext.pause();
				} else {
					this.ifPlay = true;
					audioContext.play();
				}
			},
			changeProgress(e){
				audioContext.seek(e.detail.value);
				this.ifPlay = false;
				this.playMusic();
			},
			
		}
	}
</script>

<style>
	@import url("./index.css");
</style>
