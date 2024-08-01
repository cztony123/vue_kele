<template>
	<div class="home">
		<!-- logo图片 -->
		<div class="logo-page">
			<van-icon name="chat-o" />
		</div>
		<!-- 用户名板块 -->
		<div class="phone">
			<div >
				<van-field v-model="userName" left-icon="friends-o" v-if="" right-icon="cross" placeholder="用户名" />
				<van-icon right-icon="cross"  />
			</div>
			<!-- 密码板块 -->
			<div class="pas">
				<van-field v-model="password" left-icon="goods-collect-o" :type="isShow ? 'password' : 'text' "
					placeholder="密码" />
				<div @click="onEye">
					<van-icon name="eye-o" v-if="isShow" />
					<van-icon name="closed-eye" v-else />
				</div>
			</div>
			<!-- 登录板块 -->
			<div class="loginBtn">
				<van-button type="info" @click="loginBtn">登录</van-button>
			</div>
			<div class="switch">
				<span>用户登录</span>
				<span>|</span>
				<span>用户注册</span>
			</div>
		</div>
	</div>
</template>

<script>
	import {
		Toast
	} from 'vant';
	export default {
		data() {
			return {
				userName: '', //用户名
				password: '', //密码
				isShow: true, //隐藏显示按钮
			};
		},
		methods: {
			onEye() {
				this.isShow = !this.isShow
			},

			loginBtn() {
				if (!this.password) {
					Toast("请输密码")
				}
				if (!this.userName) {
					Toast("请输入用户名")
				}
				if (this.userName && this.password) {
					Toast("登录成功")
				}
			}
		}
	};
</script>

<style scoped lang="scss">
	body {
		width: 100%;
		height: 100%;
	}

	.home {
		height: 600px;
		width: 90%;
		position: absolute;
		top: 14%;
		left: 50%;
		transform: translateX(-50%);
	}


	.logo-page {
		margin-top: 16%;
		text-align: center;
		font-weight: 900;

		::v-deep .van-icon {
			font-size: 100px;
			font-weight: 900;

		}
	}

	.phone {
		margin-top: 30px;
		width: 100%;

		div {
			::v-deep .van-field {
				margin-top: 30px;
				border-radius: 20px;
				border: 2px solid #f00;
				width: 100%;

			}

			.van-field {
				color: #000000;
			}
		}

		.loginBtn {
			width: 100%;
			margin-top: 30px;

			.van-button {
				width: 100%;
				border-radius: 20px;
			}
		}

		.pas {
			position: relative;

			.van-icon {
				display: flex;
				position: absolute;
				top: 17px;
				right: 15px;
			}
		}
	}

	.switch {
		width: 100%;
		text-align: center;
		margin-top: 35px;
		font-size: 16px;
		padding-left: 10px;

		span {
			padding: 0 8px;
		}
	}
</style>