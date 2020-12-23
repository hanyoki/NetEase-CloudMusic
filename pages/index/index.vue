<template>
	<view class="content">
		<!-- drawer -->
		<uni-drawer
		class="drawer"
		:visible="ifShowDrawer" 
		@close="hidDrawer"
		>
			<view 
			class="drawer-main"
			>	
				<view class="status-bar"></view>
				<!-- Vip -->
				<view class="swiper-vip">
					<view class="vip-top">
						<view class="vip-name">
							开通黑胶VIP
						</view>
						<view class="vip-msg">
							会员中心
						</view>
					</view>
					<view class="vip-bottom">
						加入黑胶VIP, 立享超12项专属特权
					</view>
				</view>
				<!-- 开通 -->
				<view class="vip-handle">
					<view class="handle-left">
						<view class="left-name">
							首月开通5元
						</view>
						<view class="left-msg">
							新用户专属优惠, 快来加入吧 !
						</view>
					</view>
					<view class="handle-right">
						<text class="handle-cion text-white cuIcon-right"></text>
					</view>
				</view>
				<!-- main -->
				<view class="drawer-other">
					<!-- login -->
					<view class="drawer-login">
						<view class="login-title">
							手机电脑多端同步, 尽享海量高品质音乐
						</view>
						<view class="login-btn">
							立即登录
						</view>
					</view>
					<!-- menu -->
					<view class="other-menu">
						<view class="menu-item" v-for="(item, index) in drawerMenuList" :key="index">
							<text class="menu-icon text-red" :class="item.icon"></text>
							<view class="item-name">
								{{item.name}}
							</view>
						</view>
					</view>
				</view>
			</view>
			<!-- menu1 -->
			<view class="drawer-menu">
				<view class="menu-item" v-for="(item, index) in menuItemList" :key="index">
					<view class="menu-item-left">
						<text class="menu-item-icon text-black" :class="item.icon"></text>
						<view class="menu-item-name">
							{{item.name}}
						</view>
					</view>
					<view class="menu-item-right">
						{{item.msg}}
					</view>
				</view>	
			</view>
			<!--  -->
			<view class="drawer-bottom">
				<view class="bottom-item">
					<text class="item-icon text-black cuIcon-attention"></text>
					<view class="">
						夜间模式
					</view>
				</view>
				<view class="bottom-item">
					<text class="item-icon text-black cuIcon-settings"></text>
					<view class="">
						设置
					</view>
				</view>
				<view class="bottom-item">
					<text class="item-icon text-black cuIcon-pullright"></text>
					<view class="">
						退出
					</view>
				</view>
			</view>
		</uni-drawer>
		<!-- header -->
		<Header 
		:current="swiperCurrent" 
		@changeView="changeView"
		@showDrawer="showDrawer"
		></Header>
		<!-- tab选项卡实现 -->
		<swiper
		class="main-swiper"
		:indicator-dots="false"
		:autoplay="false"
		:current="swiperCurrent"
		@change="changeCurrent"
		>
			<swiper-item>
				<scroll-view scroll-y="true" style="height: 100%;">
					<Mine></Mine>
				</scroll-view>
			</swiper-item>
			<swiper-item>
				<scroll-view scroll-y="true" style="height: 100%;">
					<Find></Find>
				</scroll-view>
			</swiper-item>
			<swiper-item>
				<scroll-view scroll-y="true" style="height: 100%;">
					<Yuncun></Yuncun>
				</scroll-view>
			</swiper-item>
			<swiper-item>
				<scroll-view scroll-y="true" style="height: 100%;">
					<Video></Video>
				</scroll-view>
			</swiper-item>
		</swiper>

		<!-- BottomBar -->
		<BottomBar></BottomBar>
	</view>
</template>

<script>
	import uniDrawer from '../../components/uni-drawer/uni-drawer.vue'
	import Header from '../../components/Header/index.vue';
	import BottomBar from '../../components/BottomBar/index.vue';
	import Find from '../../components/Find/index.vue';
	import Mine from '../../components/Mine/index.vue';
	import Yuncun from '../../components/Yuncun/index.vue';
	import Video from '../../components/Video/index.vue';
	export default {
		components:{
			uniDrawer,
			Header,
			BottomBar,
			Find,
			Mine,
			Yuncun,
			Video
		},
		data() {
			return {
				ifShowDrawer: false,
				swiperCurrent: 1,
				drawerMenuList:[{
						'id': 0,
						'name': '我的消息',
						'icon': 'cuIcon-mail'
					},{
						'id': 1,
						'name': '我的好友',
						'icon': 'cuIcon-friend'
					},{
						'id': 2,
						'name': '个人主页',
						'icon': 'cuIcon-home'
					},{
						'id': 3,
						'name': '个性装扮',
						'icon': 'cuIcon-clothes'
					},
				],
				menuItemList:[{
						'id': 0,
						'icon': 'cuIcon-magic',
						'name': '听歌识曲',
						'msg': '可识别其他app歌曲'
					},{
						'id': 1,
						'icon': 'cuIcon-ticket',
						'name': '演出',
						'msg': ''
					},{
						'id': 2,
						'icon': 'cuIcon-shop',
						'name': '商城',
						'msg': ''
					},{
						'id': 3,
						'icon': 'cuIcon-location',
						'name': '附近的人',
						'msg': ''
					},{
						'id': 4,
						'icon': 'cuIcon-discover',
						'name': '游戏推荐',
						'msg': ''
					},{
						'id': 5,
						'icon': 'cuIcon-notice',
						'name': '口袋铃铛',
						'msg': ''
					},{
						'id': 6,
						'icon': 'cuIcon-cart',
						'name': '我的订单',
						'msg': ''
					},{
						'id': 7,
						'icon': 'cuIcon-time',
						'name': '定时停止播放',
						'msg': ''
					},{
						'id': 8,
						'icon': 'cuIcon-scan',
						'name': '扫一扫',
						'msg': ''
					},{
						'id': 9,
						'icon': 'cuIcon-countdown',
						'name': '音乐闹钟',
						'msg': ''
					},{
						'id': 10,
						'icon': 'cuIcon-wifi',
						'name': '在线听歌免流量',
						'msg': ''
					},{
						'id': 11,
						'icon': 'cuIcon-choiceness',
						'name': '优惠券',
						'msg': ''
					}
				],
			}
		},
		onLoad() {
			
		},
		methods: {
			changeCurrent(e){
				this.swiperCurrent = e.detail.current;
			},
			changeView(e){
				this.swiperCurrent = e;
			},
			showDrawer(e){
				this.ifShowDrawer = e;
				
			},
			hidDrawer(){
				this.ifShowDrawer = false;
			},
		}
	}
</script>

<style>
	@import url("./index.css");
</style>
