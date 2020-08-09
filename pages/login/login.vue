<template>
	<view class="login-form">
		<form @submit="" @reset="">
			<view class="uni-form-item uni-column">
				<view class="title">账号</view>
				<input class="uni-input" name="input" placeholder="请输入账号" />
			</view>
			<view class="uni-form-item uni-column xbj">
				<view class="title">密码</view>
				<input class="uni-input" name="input" password placeholder="请输入密码" />
			</view>
		<!-- 	<view class="uni-form-item uni-column">
				<radio-group name="radio">
					<label>
						<radio value="radio1" /><text>卖家</text>
					</label>
					<label>
						<radio value="radio2" /><text>卖家</text>
					</label>
				</radio-group>
			</view> -->
			<navigator url="../guide/guide">
				<button form-type="submit">登录</button>
			</navigator>
			<button form-type="submit" style="margin-top: 15px;">注册</button>
		</form>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	
	.xbj {
		margin-bottom: 40px;
	}
	
	.uni-form-item .title {
        padding: 20px 0;
    }
	
	page {
		background: #F4F5F6;
	}
	
	.login-form {
		margin-top: 20px;
		padding: 20px;
	}
</style>
