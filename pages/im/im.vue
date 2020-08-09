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
						<uni-tag :text="item.state" size="small" type="primary"></uni-tag>
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
	import uniTag from "@/components/uni-tag/uni-tag.vue"
	const imListData = require("../../static/json/imList.json");
	export default {
		data() {
			return {
				listData: imListData.imList,
			}
		},
		components: {
			uniTag
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
	.imList:last-child .itemMiddle {
		border-bottom: 0px;
	}

	.itemMiddle {
		flex: 1;
		display: flex;
		padding: 5px 0 5px 10px;
		border-bottom: #dcdcdc 1px solid;
	}

	.mContent {
		flex: 1;
	}

	.contentUName {
		font-size: 16px;
		font-weight: 600;
		color: #3B4144
	}
	.uni-tag {
		padding:0 5px;
		margin-left: 5px;
		display: inline-block;
	}

	.contentPName,
	.contenPDetail {
		color: #646566;
	}


	.time {
		width: 40px;
	}
</style>
