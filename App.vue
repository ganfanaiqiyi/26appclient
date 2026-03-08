<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
			// #ifdef H5
			uni.getSystemInfo({
				success(e) {
					/* 窗口宽度大于420px且不在PC页面且不在移动设备时跳转至 PC.html 页面 */
					if (
						e.windowWidth > 420 &&
						!window.top.isPC &&
						!/iOS|Android/i.test(e.system)
					) {
						// 跳转到PC端专用页面
						window.location.pathname = "/static/html/pc.html";
					}
				},
			});
			// #endif
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style lang="scss">
	/*每个页面公共css */

	/* #ifdef H5 */
	page {
		background-color: #141414;
	}

	/* #endif */
</style>