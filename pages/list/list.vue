<template>
	<view>
		 <scroll-view class="scroll-view_H" scroll-x="true" @scroll="" scroll-left="120">
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
		</scroll-view>
		<view class="scroll-view-item_H">
			<view class="scroll-view-item_H uni-bg-red">A</view>
			<view class="scroll-view-item_H uni-bg-green">B</view>
			<view class="scroll-view-item_H uni-bg-blue">C</view>
		</view>
		<view class="search-block">
			<text class="ybj">推荐</text>
			<text>更新</text>
		</view>
		<!-- <view class="search-block">
			<view class="search-ico-wapper">
				<icon type="search" size="26"/>
			</view>
			<input type="text" value="" placeholder="点击输入搜索内容" class="search-text" maxlength="10" focus/>
		</view> -->
		<view class="uni-flex uni-column xqylbbj">
			<view class="flex-item flex-item-V uni-bg-red xqylb">
				<navigator url="../detail/detail">
					详情页
				</navigator>
			</view>
			<view class="flex-item flex-item-V uni-bg-green xqylb">
				列表项1
			</view>
			<view class="flex-item flex-item-V uni-bg-blue xqylb">
				列表项2
			</view>
		</view>
	</view>
</template>

<script>
	export default {
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
			}
		}
	}
</script>

<style>
	
	page {
		background-color: #F4F5F6;
	}
	
	.topnav {
		display: flex;
	}
	
	.ybj {
		margin-right: 20px;
	}
	
	.xqylbbj {
		margin: 0 10px;
	}
	
	.xqylb {
		border-bottom: 1px dashed;
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
