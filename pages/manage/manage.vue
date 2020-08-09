<template>
	<view class="container">
		<!-- 头部导航 -->
		<view class="head">
			<view class="headItem" v-for="(item, index) in headList" :key="index+item">
				<span class="headText">{{item}}</span>
			</view>
		</view>

		<!-- 分类导航 -->
		<view class="navBar">
			<button class="navItem" size="mini">{{navList[0]}}</button>
			<button :class="{'navItem': true, 'selected': isShowIng}" size="mini" @click="handleIng()">{{navList[1]}}</button>
			<button :class="{'navItem': true, 'selected': isShowEnd}" size="mini" @click="handleEnd()">{{navList[2]}}</button>
			<button class="navItem" size="mini">{{navList[3]}}</button>
		</view>

		<!-- 进行中订单 -->
		<view class="orderList" v-show="isShowIng" v-for="(item, index) in orderList" :key="index+item">
			<view class="listItem">
				<!-- item上部分 -->
				<view class="itemTop">
					<view class="itemTitle">
						<span v-if="item.isFast" class="fast">急</span>
						{{item.title}}
						<uni-tag :text="item.state" size="small" type="primary"></uni-tag>
					</view>
					<view class="blank" />
					<view class="money">
						<span class="total">{{item.total}}</span>
						<span class="security">定金{{item.security}}</span>
					</view>
				</view>
				<!-- item中间 -->
				<view class="itemMiddle">
					<view class="itemDetail">{{ item.detail | detailFilter(item.detail)}}</view>
					<button size="mini">去沟通</button>
				</view>

				<!-- 进度条 -->
				<view class="itemBottom">
					<slider :value="item.rate" min="0" max="100" show-value />
					<!-- <span>{{item.rate}}%</span> -->
					<span style="margin-left: -15px;">%</span>
					<span class="time">{{item.ddl}}</span>
				</view>
				
			</view>
		</view>
		
		<!-- 已完成订单 -->
		<view class="orderList" v-show="isShowEnd" v-for="(item, index) in orderList" :key="item+index">
			<view class="listItem">
				<!-- item上部分 -->
				<view class="itemTop">
					<view class="itemTitleEnd">
						<span class="fast">急</span>
						{{item.title}}
						<uni-tag text="已完成" size="small" type="primary"></uni-tag>
					</view>
					<view class="blank" />
					<span class="time">{{item.ddl}}</span>
				</view>
				<!-- item中间 -->
				<view class="itemMiddleEnd">
					<view class="itemDetail">{{ item.detail | detailFilter(item.detail)}}</view>
					<view class="money">
						<span class="total">{{item.total}}</span>
					</view>
				</view>
		
				<!-- 进度条 -->
				<view class="itemBottomEnd">
					<span class="score">4.8分</span>
					<span class="comment">{{item.comment}}</span>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	import uniTag from "@/components/uni-tag/uni-tag.vue"

	const orderList = require("../../static/json/orderList.json");
	export default {
		data() {
			return {
				headList: ['我的项目', '我的收藏', '我看过的'],
				navList: ['已投标', '进行中', '已完成', '全部'],
				orderList: orderList.orderList,
				isShowIng: true,
				isShowEnd: false,
			}
		},
		filters: {
			detailFilter(data) {
				const fontLength = 15;
				if (data.length > fontLength) {
					return data.substring(0, fontLength) + '...'
				}
			}
		},
		methods: {
			handleIng() {
				this.isShowIng = true;
				this.isShowEnd = false;
				
			},
			handleEnd() {
				this.isShowEnd = true;
				this.isShowIng = false;
			},
			sliderChange(e) {
				console.log(e)
				// this.orderList[index].rate = e.detail.value;
			},
		}
	}
</script>

<style>
	.container {
		padding: 15px;
		font-size: 14px;
	}

	/* 头部导航 */
	.head {
		display: flex;
		align-items: center;
		font-size: 20px;
		padding-bottom: 10px;
		border-bottom: #dcdcdc 2px solid;
	}

	.headItem {
		flex: 1;
	}

	.headItem:first-child {
		font-size: 22px;
		font-weight: 600;
	}

	.fast {
		color: red;
		margin-right: 5px;
	}

	/* 分类导航 */
	.navBar {
		padding-top: 10px;
		display: flex;
		justify-content: space-between;
		margin-bottom: 20px;
	}

	.selected {
		font-weight: 600;
		border: #007AFF solid 1px;
	}

	/* 订单列表 */
	.listItem {
		margin: 10px 0;
	}

	.itemTop {
		display: flex;
	}

	.itemTitle, .itemTitleEnd {
		font-size: 16px;
		font-weight: 600;
		color: #3B4144
	}

	.uni-tag {
		margin-left: 10px;
		display: inline-block;
	}

	.blank {
		flex: 1;
	}

	.money {
		font-weight: 600;
		color: red;
	}

	.security {
		padding-left: 5px;
	}

	/* item中间部分 */
	.itemMiddle, .itemMiddleEnd {
		align-items: center;
		display: flex;
		color: #646566;
	}
	.itemMiddleEnd {
		padding: 5px 0;
	}

	.itemDetail {
		flex: 1;
	}
	
	/* 底部 */
	.itemBottom, .itemBottomEnd {
		/* border: #007AFF 2px solid; */
		display: flex;
		align-items: center;
		color: #646566;
	}
	.itemBottomEnd {
		padding-bottom: 20px;
	}
	slider {
		touch-action: none;
		flex: 1;
	}
	
	/* 已完成 */
	.time {
		/* border: #007AFF 2px solid; */
		padding-left: 10px;
		color: #646566;
	}
	.score {
		font-weight: 600;
		color: #4CC964;
		padding-right: 10px;
	}
</style>
