<template>
	<view class="container">
		<view class="imList" v-for="(item, index) in listData" :key="item.mId">
			<view class="itemLeft">
				<img :src="item.uHead">
			</view>
			<view class="itemMiddle">
				<view class="mContent">
					<view class="contentUName">
						{{item.uName}}
					</view>
					<view class="contentPName">
						{{item.pName}}
					</view>
					<view class="contenPDetail">
						{{ item.pDetail | detailFilter(item.pDetail)}}
					</view>
				</view>
				<view class="time">
					{{item.time}}
				</view>
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

		},
		filters: {
			detailFilter(data) {
				const fontLength = 15;
				if (data.length > fontLength) {
					return data.substring(0, fontLength) + '...'
				}
			}

		}
	}
</script>

<style>
	.container {
		padding: 15px;
		font-size: 14px;
	}

	.imList {
		display: flex;
		padding-top: 5px;
	}

	/* 列表项 */
	.itemLeft {
		width: 60px;
		height: 60px;
		overflow: hidden;
		border: #3F536E 1px solid;
		position: relative;
	}
	img {
		height: 80px;
	}

	.itemMiddle {
		flex: 1;
		display: flex;
		padding: 5px 0 5px 10px;
		border-bottom: #dcdcdc 1px solid;
	}
	.imList:last-child .itemMiddle {
		border-bottom: 0px;
	}

	.mContent {
		flex: 1;
	}
	.contentUName {
		font-size: 16px;
		font-weight: 600;
		color: #3B4144
	}
	.contentPName, .contenPDetail {
		color: #646566;
	}


	.time {
		width: 40px;
	}
</style>
