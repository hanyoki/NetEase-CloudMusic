<template name="Yuncun">
	<view class="yuncun">
		<!-- nav -->
		<view class="yuncun-nav">
			<view class="nav-square selected">
				广场
			</view>
			<view class="nav-follow">
				关注
			</view>
		</view>
		<!-- yuncun-top-card -->
		<view class="yuncun-top-card">
			<view class="top-card-left">
				<view class="card-left-title">
					云村热评墙&nbsp;&nbsp; >
				</view>
				<view class="card-left-msg">
					村友,原来大家都在云村看这些评论
				</view>
			</view>
			<view class="top-card-right">
				<view class="card-right-title">
					Mar.
				</view>
				<view class="card-right-msg">
					11
				</view>
			</view>
		</view>
		<!-- video-card -->
		<view class="yuncun-video-card">
			<view class="video-card" v-for="(item, index) in videoList" :key="index" @tap="goPlay">
				<image class="video-card-image" :src="item.img" mode=""></image>
				<view class="video-card-comm">
					{{item.comm}}
				</view>
				<view class="video-card-bottom">
					<view class="card-bottom-left">
						<image class="card-bottom-image" :src="item.uimg" mode=""></image>
						<view class="card-bottom-name">
							{{item.uname}}
						</view>
					</view>
					<view class="card-bottom-right">
						<view class="card-bottom-num">
							{{item.num}}万赞
						</view>
						<text class="card-bottom-icon text-gray cuIcon-moreandroid"></text>
					</view>
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
		name: "Yuncun",
		props:{},
		data() {
			return{
				videoList:[{
						'id': 0,
						'img': 'http://p2.music.126.net/VDN3UgDoNu_2t1Bm46t54A==/109951164777422663.jpg?param=140y140',
						'comm': '宇宙星河浪漫，生活温柔且可爱',
						'uimg': 'http://p2.music.126.net/VDN3UgDoNu_2t1Bm46t54A==/109951164777422663.jpg?param=140y140',
						'uname': '情思天鹅',
						'num': 18
					},{
						'id': 1,
						'img': 'http://p2.music.126.net/eHIjIFGwsSNzIIEaaXaeww==/109951164517305229.jpg?param=140y140',
						'comm': '白噪追溯 | 青年文艺复古风潮',
						'uimg': 'http://p2.music.126.net/eHIjIFGwsSNzIIEaaXaeww==/109951164517305229.jpg?param=140y140',
						'uname': '情感图文君',
						'num': 3.4
					},{
						'id': 2,
						'img': 'http://p2.music.126.net/drP4yfrXEGGo0cSSAH11CQ==/109951164766781648.jpg?param=140y140',
						'comm': '日系|舍不得离开 让我怎么能不喜欢',
						'uimg': 'http://p2.music.126.net/drP4yfrXEGGo0cSSAH11CQ==/109951164766781648.jpg?param=140y140',
						'uname': '川诗鸢',
						'num': 4.2
					},{
						'id': 3,
						'img': 'http://p1.music.126.net/JEYDQ6MV0C-dPqiqojQibw==/109951164442575315.jpg?param=140y140',
						'comm': '月亮不抱你 时光摧毁你 可我还是想爱你',
						'uimg': 'http://p1.music.126.net/JEYDQ6MV0C-dPqiqojQibw==/109951164442575315.jpg?param=140y140',
						'uname': '樱桃味音乐',
						'num': 91
					},{
						'id': 4,
						'img': 'http://p1.music.126.net/tb9Q9Of3fXG7-v8OpPhsEQ==/109951164676901776.jpg?param=140y140',
						'comm': '生活是自己的 尽情享受 尽情可爱',
						'uimg': 'http://p1.music.126.net/tb9Q9Of3fXG7-v8OpPhsEQ==/109951164676901776.jpg?param=140y140',
						'uname': '宇宙播报机',
						'num': 70
					},{
						'id': 5,
						'img': 'http://p1.music.126.net/Wowr8upF1NKL4J7OhowaDA==/109951164624732895.jpg?param=140y140',
						'comm': '<歌荒清除>接下来将拨动你的心弦',
						'uimg': 'http://p1.music.126.net/Wowr8upF1NKL4J7OhowaDA==/109951164624732895.jpg?param=140y140',
						'uname': 'hentai小绅士',
						'num': 113
					},{
						'id': 6,
						'img': 'http://p2.music.126.net/XGypVYOfRuURXO3SuKS4gg==/109951164645704530.jpg?param=140y140',
						'comm': '【旋律电子】让跃动的彩虹激活你的心灵！',
						'uimg': 'http://p2.music.126.net/XGypVYOfRuURXO3SuKS4gg==/109951164645704530.jpg?param=140y140',
						'uname': '谐星七十六号',
						'num': 83
					},{
						'id': 7,
						'img': 'http://p1.music.126.net/NaFSh7IoQOtpocDX164JRQ==/109951164645893553.jpg?param=140y140',
						'comm': '一起听说唱好听到爆',
						'uimg': 'http://p1.music.126.net/NaFSh7IoQOtpocDX164JRQ==/109951164645893553.jpg?param=140y140',
						'uname': '力OG',
						'num': 565
					},{
						'id': 8,
						'img': 'http://p1.music.126.net/UX78eEDic19VjIwf2e_MGw==/109951164491173755.jpg?param=140y140',
						'comm': '时光之旅 | 致你我年少时的回忆',
						'uimg': 'http://p1.music.126.net/UX78eEDic19VjIwf2e_MGw==/109951164491173755.jpg?param=140y140',
						'uname': '少年的半岛铁盒',
						'num': 567
					},{
						'id': 9,
						'img': 'http://p1.music.126.net/FJN_RF5TBEi4h5wFp8jY2w==/109951164498175594.jpg?param=140y140',
						'comm': '要不要买菜',
						'uimg': 'http://p1.music.126.net/FJN_RF5TBEi4h5wFp8jY2w==/109951164498175594.jpg?param=140y140',
						'uname': 'Z舍曲林z',
						'num': 35
					},{
						'id': 10,
						'img': 'http://p1.music.126.net/1V4NtO48QSLDOth4W_GfSg==/109951164731614024.jpg?param=140y140',
						'comm': '抖音民谣姑娘收录',
						'uimg': 'http://p1.music.126.net/1V4NtO48QSLDOth4W_GfSg==/109951164731614024.jpg?param=140y140',
						'uname': '白羊and摩羯',
						'num': 3.5
					},{
						'id': 11,
						'img': 'http://p1.music.126.net/zk3QExfjxafpWTKu0DZsGA==/109951164717393424.jpg?param=140y140',
						'comm': '私藏 | 值得循环的Cover合集',
						'uimg': 'http://p1.music.126.net/zk3QExfjxafpWTKu0DZsGA==/109951164717393424.jpg?param=140y140',
						'uname': ' 她的水彩笔',
						'num': 4.7
					},{
						'id': 12,
						'img': 'http://p1.music.126.net/a-dXHVgZKqjMjEvQ6vBYRw==/109951164750647901.jpg?param=140y140',
						'comm': '怎么办我忘不掉她',
						'uimg': 'http://p1.music.126.net/a-dXHVgZKqjMjEvQ6vBYRw==/109951164750647901.jpg?param=140y140',
						'uname': ' 压抑疼',
						'num': 14
					},{
						'id': 13,
						'img': 'http://p1.music.126.net/EFlgfCY5i8itcc-H_1bKEw==/109951164728192899.jpg?param=140y140',
						'comm': '任往事随风',
						'uimg': 'http://p1.music.126.net/EFlgfCY5i8itcc-H_1bKEw==/109951164728192899.jpg?param=140y140',
						'uname': ' 搞笑的酸葡萄',
						'num': 2.1
					},{
						'id': 14,
						'img': 'http://p1.music.126.net/RbzjboFAEsGDyY43FND4MA==/109951164668566359.jpg?param=140y140',
						'comm': 'Monstercat - 学习 | 音乐让你更有效率',
						'uimg': 'http://p1.music.126.net/RbzjboFAEsGDyY43FND4MA==/109951164668566359.jpg?param=140y140',
						'uname': ' Monstercat',
						'num': 21
					},{
						'id': 15,
						'img': 'http://p1.music.126.net/yV0aGwYf3zsw-u-skDF4mw==/109951164731490209.jpg?param=140y140',
						'comm': '考研路上激励自己的歌（持续更新）',
						'uimg': 'http://p1.music.126.net/yV0aGwYf3zsw-u-skDF4mw==/109951164731490209.jpg?param=140y140',
						'uname': '博儿要努力奋斗up',
						'num': 11
					},{
						'id': 16,
						'img': 'http://p1.music.126.net/gf3_nE6wPprWHk1V-To7vA==/109951164649022295.jpg?param=140y140',
						'comm': '好听到单曲循环的英文歌曲',
						'uimg': 'http://p1.music.126.net/gf3_nE6wPprWHk1V-To7vA==/109951164649022295.jpg?param=140y140',
						'uname': '白羊and摩羯',
						'num': 19
					},{
						'id': 17,
						'img': 'http://p1.music.126.net/yT8XIUfu3VBGpmD374clzQ==/109951164733050144.jpg?param=140y140',
						'comm': '打游戏专用',
						'uimg': 'http://p1.music.126.net/yT8XIUfu3VBGpmD374clzQ==/109951164733050144.jpg?param=140y140',
						'uname': '慕辰si了',
						'num': 10
					},{
						'id': 18,
						'img': 'http://p1.music.126.net/UyQgj_FLyHrbqnZGBVAmmQ==/109951164591919152.jpg?param=140y140',
						'comm': '治愈纯音｜在孤独中找到自我',
						'uimg': 'http://p1.music.126.net/UyQgj_FLyHrbqnZGBVAmmQ==/109951164591919152.jpg?param=140y140',
						'uname': '我最近又膨胀了',
						'num': 11
					},{
						'id': 19,
						'img': 'http://p1.music.126.net/AAY3fugfnxVyi6TFRUaNJg==/109951164729013265.jpg?param=140y140',
						'comm': '硬曲 硬不硬听了再说（蹦迪专用）',
						'uimg': 'http://p1.music.126.net/AAY3fugfnxVyi6TFRUaNJg==/109951164729013265.jpg?param=140y140',
						'uname': '陪雨柔长大',
						'num': 24
					},{
						'id': 20,
						'img': 'http://p1.music.126.net/qnLwtGqBLGXw9ArI1P8TVQ==/109951164721601587.jpg?param=140y140',
						'comm': '一秒沦陷 | 超好听的Remix',
						'uimg': 'http://p1.music.126.net/qnLwtGqBLGXw9ArI1P8TVQ==/109951164721601587.jpg?param=140y140',
						'uname': '全世界皆你',
						'num': 18
					},
					
				]
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
