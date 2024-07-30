<template>
	<div class="home">
		<div class="logo-page">
			<van-icon name="chat-o" size="3rem" />
		</div>
		<div class="phone">
			<van-field v-model="text" label="文本" />
			<van-field v-model="password" type="password" label="密码" />
		</div>
	</div>
</template>

<script>
</script>

<style scoped lang="scss">
	body {
		width: 100%;
		height: 100%;
	}
	.home {
		border: 2px solid #00ff00;
		height: 600px;
		width: 350px;
		position: absolute;
		top: 15%;
		margin: 8% 8%;
	}
	.logo-page{
		margin-top: 20%;
		text-align: center;
		font-weight: 900;
		::v-deep .van-icon{
			font-size: 3px;
			font-weight: 900;
			color: #00ff00;
		}
	}
	::van-icon{
		
		
	}
</style>