<template>
	<view>
<!-- 		 <scroll-view class="scroll-view_H" scroll-x="true" @scroll="" scroll-left="120">
			<view id="demo1" class="scroll-view-item_H uni-bg-red xhx">
				<navigator url="../login/login">
					<text>首页</text>
				</navigator>
			</view><view id="demo1" class="scroll-view-item_H uni-bg-red">
				标签2
			</view><view id="demo1" class="scroll-view-item_H uni-bg-red">
				标签3
			</view><view id="demo1" class="scroll-view-item_H uni-bg-red">
				标签4
			</view><view id="demo1" class="scroll-view-item_H uni-bg-red">
				标签5
			</view>
		</scroll-view> -->
		<view class="scroll-view_H">
			<view class="scroll-view-item_H uni-bg-red xhx">
				<navigator url="../login/login">
					<text>ps</text>
				</navigator>
			</view>
			<view class="scroll-view-item_H uni-bg-green">Excel</view>
			<view class="scroll-view-item_H uni-bg-blue">Word</view>
			<view class="scroll-view-item_H uni-bg-blue">...</view>
		</view>
		<view class="search-block">
			<text class="ybj">推荐</text>
			<text>更新</text>
		</view>
		<view class="uni-flex uni-column xqylbbj">
			<uni-card 
			    title="制作一份海报" 
				:mode="title"
			    :is-shadow="true" 
			    extra="截止日期:2020-08-09" 
			    note="Tips"
				v-for="n in 3"
				:key="n"
				@click="test"
			>
			   <text class="list-content-font">我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容</text>
			   <template v-slot:footer>
					<view class="tag-list">
						<uni-tag text="标签1" type="primary" :inverted="true" class="tag-style"></uni-tag>
						<uni-tag text="标签2" type="primary" :inverted="true" class="tag-style"></uni-tag>
				   </view>
					<text class="list-float-rmb">￥100</text>
			   </template>
			</uni-card>
		</view>
	</view>
</template>

<script>
	import uniTag from "@/components/uni-tag/uni-tag.vue"
	import uniCard from '@/components/uni-card/uni-card.vue'
	export default {
		components: {uniTag, uniCard},
		data() {
			return {
				scrollTop: 0,
				old: {
					scrollTop: 0
				}
			}
		},
		methods: {
			scroll: function(e) {
				console.log(e)
				this.old.scrollTop = e.detail.scrollTop
			},
			test() {
				uni.navigateTo({
				    url: '/pages/detail/detail'
				});
			}
		}
	}
</script>

<style>
	
	page {
		background-color: #F4F5F6;
	}
	
	.list-content-font {
		font-size: 14px;
	}
	
	.tag-list {
		display: flex;
	}
	
	.tag-style {
		width: 40px;
		margin-right: 5px;
	}
	
	.list-content {
		display: flex;
		text-indent: 2em;
	}

	.list-content-text {
		margin: 10px;
	}

	.list-content-xin {
		line-height: 70px;
		margin: 0 10px;
		color: red;
		font-size: 30px;
	}
	
	.list-title-time {
		float: right;
		font-size: 15px;
	}
	
	.list-float-rmb {
		float: right;
		color: #FF0000;
	}
	
	.topnav {
		display: flex;
	}
	
	.ybj {
		margin-right: 20px;
	}
	
	.xqylbbj {
		/* margin: 0 10px; */
	}
	
	.xqylb {
		/* border-bottom: 1px dashed; */
		background-color: #fff;
		margin-top: 15px;
	}
	
	.xhx {
		border-bottom: 1px solid;
	}

	.scroll-view_H {
		white-space: nowrap;
		width: 100%;
		background-color: #ffffff;
	}

	.scroll-view-item_H {
		display: inline-block;
		width: 100px;
		height: 50px;
		line-height: 50px;
		text-align: center;
		font-size: 18px;
	}
	
	.flex-item {
		width: 33.3%;
		height: 200rpx;
		text-align: center;
		line-height: 200rpx;
	}

	.flex-item-V {
		width: 100%;
		height: 150rpx;
		text-align: center;
		line-height: 150rpx;
	}
	
	.search-text{
		font-size: 18px;
		/* background-color: #FFFFFF; */
		height: 60upx;
		width: 480upx;
		margin-left: 10px;
	}
	
	.search-block{
		padding: 0 15px;
		margin: 10px 10px 0;
	}
	
	
</style>
