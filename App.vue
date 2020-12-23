<script>
	export default {
		onLaunch: function() {
			console.log('App Show')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	@import url("./colorui/icon.css");
	@import url("./colorui/main.css");
	/*每个页面公共css */
	page{
		width: 100%;
		height: 100%;
	}
	.content{
		width: 100%;
		height: 100%;
		background-color: #FFFFFF;
		color: #000000;
		box-sizing: border-box;
		position: relative;
		display: flex;
		flex-direction: column;
	}
</style>
