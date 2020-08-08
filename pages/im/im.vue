<template>
	<view class="container">
		<view class="imList" v-for="(item, index) in listData" :key="item.mId">
			<view class="itemLeft">
				head
			</view>
			<view class="content">
				<view class="contentUName">
					{{item.uName}}
				</view>
				<view class="contentPName">
					{{item.pName}}
				</view>
				<view class="contenPDetail">
					{{item.pDetail}}
				</view>
			</view>
			<view class="time">
				{{item.time}}
			</view>
		</view>

	</view>
</template>

<script>
	const imListData = require("../../static/json/imList.json");
	export default {
		data() {
			return {
				listData: imListData.imList,
			}
		},
		methods: {

		}
	}
</script>

<style>
	.container {
		padding: 20px;
		font-size: 14px;
	}

	.imList {
		display: flex;
		/* height:80px; */
		border-bottom: #3F536E 1px solid;
	}
	.content {
		flex: 1;
		padding: 0 10px;
	}
</style>
