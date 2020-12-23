<template name="Find">
	<view class="find">
		<!-- swiper -->
		<swiper 
		class="find-swiper"
		:indicator-dots="false" 
		:autoplay="true" 
		:interval="3000" 
		:duration="1000"
		circular="true"
		vertical="true"
		>
			<swiper-item 
			v-for="(item, index) in swpierList" 
			:key="index"
			>
				<image :src="item.img" mode="" @tap="goPlay"></image>
			</swiper-item>
		</swiper>
		<!-- category -->
		<view class="find-category">
			<view class="type">
				<view class="type-icon">
					<text class="text-white cuIcon-font"></text>
				</view>
				<view class="type-name">
					每日推荐
				</view>
			</view>
			<view class="type">
				<view class="type-icon">
					<text class="text-white cuIcon-radioboxfill"></text>
				</view>
				<view class="type-name">
					歌单
				</view>
			</view>
			<view class="type">
				<view class="type-icon">
					<text class="text-white cuIcon-rank"></text>
				</view>
				<view class="type-name">
					排行榜
				</view>
			</view>
			<view class="type">
				<view class="type-icon">
					<text class="text-white cuIcon-musicfill"></text>
				</view>
				<view class="type-name">
					电台
				</view>
			</view>
			<view class="type">
				<view class="type-icon">
					<text class="text-white cuIcon-servicefill"></text>
				</view>
				<view class="type-name">
					私人FM
				</view>
			</view>
		</view>
		<!-- more choise -->
		<view class="find-recommend">
			推荐歌单
		</view>
		<view class="find-choise">
			<view class="choise-left">
				为你精挑细选
			</view>
			<view class="choise-right">
				查看更多
			</view>
		</view>
		<!-- choise list -->
		<view class="find-choise-list">
			<view class="choise-item" v-for="(item, index) in audioList1" :key="index" @tap="goPlay">
				<image :src="item.img" mode=""></image>
				<view class="choise-title">
					{{item.title}}
				</view>
			</view>
		</view>
		
		<!-- more choise -->
		<!-- style list -->
		<view class="find-recommend">
			风格推荐
		</view>
		<view class="find-choise">
			<view class="choise-left">
				聆听华语佳曲
			</view>
			<view class="choise-right">
				查看更多
			</view>
		</view>
		<view class="find-style-list">
			<view class="style-item" v-for="(item, index) in audioList2" :key="index" @tap="goPlay">
				<image :src="item.img" mode=""></image>
				<view class="style-info">
					<view class="style-title">
						{{item.title}}
					</view>
					<view class="style-msg">
						超71%人播放
					</view>
				</view>
				<view class="style-icon">
					<text class="text-red cuIcon-playfill" @tap="goPlay"></text>
				</view>
			</view>
		</view>
		<!-- screen recommend -->
		<view class="find-recommend">
			场景推荐
		</view>
		<view class="find-choise">
			<view class="choise-left">
				晚霞灿烂 音乐惬意
			</view>
			<view class="choise-right">
				查看更多
			</view>
		</view>
		<view class="find-choise-list">
			<view class="choise-item" v-for="(item, index) in audioList3" :key="index" @tap="goPlay">
				<image :src="item.img" mode=""></image>
				<view class="choise-title">
					{{item.title}}
				</view>
			</view>
		</view>
		<!-- new -->
		<view class="find-recommend">
			3月11日
		</view>
		<view class="find-choise">
			<view class="choise-left">
				新歌
			</view>
			<view class="choise-right">
				更多新歌
			</view>
		</view>
		<view class="find-style-list">
			<view class="style-item" v-for="(item, index) in audioList4" :key="index" @tap="goPlay">
				<image :src="item.img" mode=""></image>
				<view class="style-info">
					<view class="style-title">
						{{item.title}}
					</view>
					<view class="style-msg">
						超71%人播放
					</view>
				</view>
				<view class="style-icon">
					<text class="text-red cuIcon-playfill" @tap="goPlay"></text>
				</view>
			</view>
		</view>
		
		<!-- everyone listen -->
		<view class="find-recommend">
			大家都在听
		</view>
		<view class="find-choise">
			<view class="choise-left">
				天晴便心晴
			</view>
			<view class="choise-right">
				播放全部
			</view>
		</view>
		<view class="find-style-list">
			<view class="style-item" v-for="(item, index) in audioList5" :key="index" @tap="goPlay">
				<image :src="item.img" mode=""></image>
				<view class="style-info">
					<view class="style-title">
						{{item.title}}
					</view>
					<view class="style-msg">
						超71%人播放
					</view>
				</view>
				<view class="style-icon">
					<text class="text-red cuIcon-playfill" @tap="goPlay"></text>
				</view>
			</view>
		</view>
		<!-- 电台推荐 -->
		<view class="find-recommend">
			电台推荐
		</view>
		<view class="find-choise">
			<view class="choise-left">
				沉溺在温柔的歌声中
			</view>
			<view class="choise-right">
				查看更多
			</view>
		</view>
		<!-- choise list -->
		<view class="find-choise-list">
			<view class="choise-item" v-for="(item, index) in audioList6" :key="index" @tap="goPlay">
				<image :src="item.img" mode=""></image>
				<view class="choise-title">
					{{item.title}}
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
		name: "Find",
		props:{},
		data() {
			return {
				swpierList:[{
						'id': 0,
						'img': '../../static/images/swiper1.jpg'
					},{
						'id': 1,
						'img': '../../static/images/swiper2.jpg'
					},{
						'id': 2,
						'img': '../../static/images/swiper3.jpg'
					},{
						'id': 3,
						'img': '../../static/images/swiper4.jpg'
					},{
						'id': 4,
						'img': '../../static/images/swiper5.jpg'
					},{
						'id': 5,
						'img': '../../static/images/swiper6.jpg'
					},{
						'id': 6,
						'img': '../../static/images/swiper7.jpg'
					},{
						'id': 7,
						'img': '../../static/images/swiper8.jpg'
					},{
						'id': 8,
						'img': '../../static/images/swiper9.jpg'
					}
					
				],
				audioList1:[{
						'id': 0,
						'title': '优质的翻唱男声',
						'img': 'http://p1.music.126.net/TUBlMnKtrTmtyK3T0up3JA==/109951164712687908.jpg?param=140y140'
					},{
						'id': 1,
						'title': '春日鸡血丨躺在床上虚度人生是不正确的',
						'img': 'http://p1.music.126.net/8Tm-Jbh8un2zngCQKGNcmA==/109951164785517450.jpg?param=140y140'
					},{
						'id': 2,
						'title': '精选翻唱：热爱万物，无例外无最爱',
						'img': 'http://p1.music.126.net/dTkcVDEug3vcWqSeg_xKwg==/109951164737622185.jpg?param=140y140'
					}	
				],
				audioList2:[{
						'id': 0,
						'title': '黑白琴键下的绝美女声',
						'img': 'http://p1.music.126.net/y1bh4u1mOpVeno1ncddQ4Q==/109951162847551273.jpg?param=140y140'
					},{
						'id': 1,
						'title': '宇宙星河浪漫，生活温柔且可爱',
						'img': 'http://p1.music.126.net/VDN3UgDoNu_2t1Bm46t54A==/109951164777422663.jpg?param=140y140'
					},{
						'id': 2,
						'title': '日系|舍不得离开 让我怎么能不喜欢',
						'img': 'http://p1.music.126.net/drP4yfrXEGGo0cSSAH11CQ==/109951164766781648.jpg?param=140y140'
					}	
				],
				audioList3:[{
						'id': 0,
						'title': '『纯音乐』银光洒向城市与山涧',
						'img': 'http://p1.music.126.net/43rqv8Legut8dbvXsTZC6Q==/109951164473011350.jpg?param=140y140'
					},{
						'id': 1,
						'title': '熬夜写作业必备醒脑歌单（英文）',
						'img': 'http://p1.music.126.net/OUFpNEOPyNE6zZSogqse2Q==/109951164625068258.jpg?param=140y140'
					},{
						'id': 2,
						'title': '你绝对熟悉的电音|自嗨蹦迪',
						'img': 'http://p1.music.126.net/jyEBx1l6iukbWTB9TKvCFg==/109951164412824316.jpg?param=140y140'
					}	
				],
				audioList4:[{
						'id': 0,
						'title': '网易云评论最多纯音TOP50',
						'img': 'http://p1.music.126.net/EQ8nQ7V9D5oUbQ927sCoRQ==/109951164507615158.jpg?param=140y140'
					},{
						'id': 1,
						'title': '李信-上单节奏战歌',
						'img': 'http://p1.music.126.net/gciPLrfPiDm6y-xx1sSJuQ==/109951164691494129.jpg?param=140y140'
					},{
						'id': 2,
						'title': '中国摇滚30年图鉴：永远年轻 永远热泪盈眶',
						'img': 'http://p1.music.126.net/7TPPvYN62ki-6U8CE7B8bQ==/109951164513274541.jpg?param=140y140'
					}	
				],
				audioList5:[{
						'id': 0,
						'title': '游戏战歌。没有撤退可言',
						'img': 'http://p1.music.126.net/1DojAsWTA59yh4tXlW31Ow==/109951164483215571.jpg?param=140y140'
					},{
						'id': 1,
						'title': '100种民谣女声 带你去感受星辰万物',
						'img': 'http://p1.music.126.net/ipDaITvu_vVvHJqxaujLUQ==/109951164441184008.jpg?param=140y140'
					},{
						'id': 2,
						'title': '我们终将长大远行，去那广阔世界闯荡',
						'img': 'http://p1.music.126.net/WlkmTxQZOi_gn_Kduo_6hg==/109951164545499934.jpg?param=140y140'
					}	
				],
				audioList6:[{
						'id': 0,
						'title': '晓苏电台',
						'img': 'http://p2.music.126.net/Gdh7VcGd22emCGjHiNMgtw==/3439272373022999.jpg?param=200y200'
					},{
						'id': 1,
						'title': '糖蒜音乐故事',
						'img': 'http://p2.music.126.net/-yxaZ-D3khs-I_4g4bbS2g==/109951163509540918.jpg?param=200y200'
					},{
						'id': 2,
						'title': '谜醉音乐FM',
						'img': 'http://p2.music.126.net/6f7CYHub_qBA5YVGKIsz1g==/109951164183335672.jpg?param=200y200'
					}	
				],
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
