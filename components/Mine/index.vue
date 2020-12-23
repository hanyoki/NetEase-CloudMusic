<template name="Mine">
	<view class="mine">
		<!-- user info -->
		<view class="mine-user">
			<view class="user-info">
				<view class="user-ico">
					<text class="user-icon text-black cuIcon-people"></text>
				</view>
				<view class="user-msg">
					登录立享手机电脑多端同步
				</view>
			</view>
			<view class="user-login">
				立即登录
			</view>
		</view>
		<!-- user category -->
		<view class="user-category">
			<view class="cate-class" v-for="(item, index) in cateList" :key="index">
				<text class="cate-icon text-black" :class="'cuIcon-'+ item.icon"></text>
				<view class="cate-name">
					{{item.title}}
				</view>
			</view>
		</view>
		<!-- my new -->
		<view class="user-new-title">
			<view class="new-title">
				我的音乐
			</view>
			<text class="new-title-icon text-black cuIcon-right"></text>
		</view>
		<view class="mine-new-card">
			<view class="new-card">
				<text class="new-card-icon text-red cuIcon-likefill"></text>
				<view class="new-msg">
					我喜欢的音乐
				</view>
			</view>
			<view class="new-card">
				<text class="new-card-icon text-white cuIcon-service"></text>
				<view class="new-msg">
					私人FM
				</view>
				<view class="new-bott">
					你的私人曲库
				</view>
			</view>
			<view class="new-card">
				<text class="new-card-icon text-black cuIcon-wefill"></text>
				<view class="new-msg">
					最嗨电音
				</view>
				<view class="new-bott">
					专业电音平台
				</view>
			</view>
		</view>
		<!-- 最近播放 -->
		<view class="user-new-title">
			<view class="new-title">
				最近播放
			</view>
			<text class="new-title-icon text-black cuIcon-right"></text>
		</view>
		<view class="res-play">
			<image src="http://p2.music.126.net/JRNj03dPHidbM4jQ-HFK0A==/18826937604631903.jpg?param=200y200" mode=""></image>
			<view class="res-title">
				<view class="res-name">
					全部已播歌曲
				</view>
				<view class="res-num">
					3首
				</view>
			</view>
		</view>
		<!-- 创建歌单 -->
		<view class="user-new-title">
			<view class="new-title">
				创建歌单 0
			</view>
			<view class="new-coll">
				收藏歌单 0
			</view>
			<text class="new-title-icon text-black cuIcon-moreandroid"></text>
		</view>
		<view class="mine-create">
			<view class="create">
				+ &nbsp;&nbsp;&nbsp;导入外部歌单
			</view>
		</view>
		<!-- 推荐歌单 -->
		<view class="user-new-title">
			<view class="new-title">
				推荐歌单
			</view>
			<text class="new-title-icon text-black cuIcon-close"></text>
		</view>
		<!-- 推荐列表 -->
		<view class="mine-recommend">
			<view class="recommend" v-for="(item, index) in recommList" :key="index" @tap="goPlay">
				<image :src="item.img" mode=""></image>
				<view class="recommend-title">
					<view class="title-name">
						{{item.name}}
					</view>
					<view class="title-msg">
						{{item.msg}}
					</view>
				</view>
			</view>
		</view>
		<!-- last -->
		<view class="last">
			到底啦&nbsp;~
		</view>
	</view>
</template>

<script>
	export default {
		name: "Mine",
		props:{},
		data() {
			return {
				cateList:[{	
						'id': 0,
						'title': '本地音乐',
						'icon': 'musicfill'
					},{	
						'id': 1,
						'title': '下载管理',
						'icon': 'pulldown'
					},{	
						'id': 2,
						'title': '我的电台',
						'icon': 'service'
					},{	
						'id': 3,
						'title': '我的收藏',
						'icon': 'favor'
					},{	
						'id': 4,
						'title': '关注新歌',
						'icon': 'radioboxfill'
					}
				],
				recommList:[{
						'id': 0,
						'name': '找一个让你笑的人在一起',
						'img': 'http://p1.music.126.net/JpGpHfy_DUAWeuIQHrjYbg==/1418370012865049.jpg?param=40x40',
						'msg': '蕊希电台'
					},{
						'id': 1,
						'name': 'Bright Vachirawit - 佳偶天成（泰剧《假偶天成》原声带）',
						'img': 'http://p1.music.126.net/KlP7pLme3kvsrGGBSRk5Uw==/109951164788655217.jpg?param=40x40',
						'msg': '喜翻音乐电台CFanRadio'
					},{
						'id': 2,
						'name': '道理的道理（Live）',
						'img': 'http://p1.music.126.net/dv3ZA0DY3ySxzvL-81mucw==/109951164013911305.jpg?param=40x40',
						'msg': 'Cuphead Club'
					},{
						'id': 3,
						'name': '那丝也有春天 +刘哈哈与大先生',
						'img': 'http://p1.music.126.net/HM8HRxrfTpzICTFcvBxJyg==/109951164749337903.jpg?param=40x40',
						'msg': '叶建楠YJN'
					},{
						'id': 4,
						'name': 'Geronimo',
						'img': 'http://p1.music.126.net/BgtME1qfBLrPBioX0jIWcQ==/18462999253667789.jpg?param=40x40',
						'msg': '段弋不是戈'
					},{
						'id': 5,
						'name': '心墙',
						'img': 'http://p1.music.126.net/3OiQGgsmQpl7_q9TaPWo5A==/3376600210271961.jpg?param=40x40',
						'msg': '是你的垚'
					},
				]
			}
		},
		methods: {
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
