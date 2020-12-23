<template>
	<view class="content">
		<view class="status-bar"></view>
		<!-- serchBar -->
		<view class="search-box">
			<text class="search-box-icon text-black cuIcon-back" @tap="goBack"></text>
			<view class="search-input">
				<input
				class="input"
				type="text" 
				value=""
				focus="true"
				placeholder="大家都在搜 林宥嘉"
				placeholder-style="color:#ababab;"
				/>
			</view>
			<text class="search-box-icon text-black cuIcon-people"></text>
		</view>
		<!-- 热搜title -->
		<view class="hot-search-title">
			热搜榜
		</view>
		<!-- 热搜列表 -->
		<view class="hot-search-list">
			<view class="search-list" v-for="(item, index) in searchList" :key="index">
				<view class="search-list-left">
					<view class="search-rank">
						{{item.id}}
					</view>
					<view class="search-list-title">
						<view class="search-list-name">
							{{item.name}}
						</view>
						<view class="search-list-msg">
							{{item.msg}}
						</view>
					</view>
				</view>
				<view class="search-list-right">
					{{item.hot}}
				</view>
			</view>
		</view>
		<!-- last -->
		<view class="last">
			没有啦&nbsp;~
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				searchList:[{
						'id': 1,
						'name': '我的世界',
						'msg': '没事 我很好 眼泪没掉还能笑',
						'hot': '3085082'
					},{
						'id': 2,
						'name': 'love story',
						'msg': '很多人因这首歌爱上了霉霉吧',
						'hot': '1855744'
					},{
						'id': 3,
						'name': '281公里',
						'msg': '谢霆锋再唱20年前金曲',
						'hot': '1791665'
					},{
						'id': 4,
						'name': '我的名字',
						'msg': '焦迈奇最新专辑已上线',
						'hot': '1736960'
					},{
						'id': 5,
						'name': '起风了',
						'msg': '神仙嗓音, 超强音域跨度',
						'hot': '1664234'
					},{
						'id': 6,
						'name': '我们',
						'msg': '这首歌真的太容易让人走心',
						'hot': '1419570'
					},{
						'id': 7,
						'name': '迷人的危险',
						'msg': '温柔的声音, 释怀酸涩的情感',
						'hot': '1333577'
					},{
						'id': 8,
						'name': '只要有你',
						'msg': '好久没听了, 回味无穷',
						'hot': '1181755'
					},{
						'id': 9,
						'name': '韦礼安双栖动物',
						'msg': '没有你的日子 呼吸都成了渴求',
						'hot': '1129381'
					},{
						'id': 10,
						'name': '最佳歌手',
						'msg': '许嵩是不是大家心目中的最佳歌手呢?',
						'hot': '1116566'
					},{
						'id': 11,
						'name': '处处吻',
						'msg': '会唱这首歌的人都会发光呀',
						'hot': '955794'
					},{
						'id': 12,
						'name': '华晨宇',
						'msg': '花花的歌声里 有少年的孤傲',
						'hot': '927192'
					},{
						'id': 13,
						'name': '无期',
						'msg': '即便遥遥无期 也愿为爱的信徒',
						'hot': '844470'
					},{
						'id': 14,
						'name': '爱',
						'msg': '让我们自由自在的恋爱~',
						'hot': '811963'
					},{
						'id': 15,
						'name': '勇气',
						'msg': '希望这首歌能在冬夜里温暖你',
						'hot': '774884'
					},{
						'id': 16,
						'name': '张杰',
						'msg': '张杰带你穿越人海',
						'hot': '734624'
					},{
						'id': 17,
						'name': '太阳',
						'msg': '就算是雨神也想做太阳呀!',
						'hot': '730844'
					},{
						'id': 18,
						'name': '蓝',
						'msg': '你走后这天还是那么蓝',
						'hot': '710358'
					},{
						'id': 19,
						'name': '周深',
						'msg': '唱遍影视剧插曲的天籁歌手',
						'hot': '709265'
					},{
						'id': 20,
						'name': '朋友请听好',
						'msg': '何炅x谢娜x易烊千玺, 超治愈',
						'hot': '695341'
					},
				]
			}
		},
		methods: {
			goBack(){
				history.back()
			}
		}
	}
</script>

<style>
	@import url("./index.css");
</style>
