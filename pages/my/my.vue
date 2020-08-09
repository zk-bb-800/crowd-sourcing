<template>
	<view>
		<uni-list class="grxx">
			<uni-card 
			    title="张三" 
			    mode="title" 
			    :is-shadow="true" 
				thumbnail="../../static/images/tx.jpg"
			>
			<uni-tag text="vip" type="warning" :circle="true" :inverted="true":display="true" class="my-vip" ></uni-tag>
			
			<view class="wd">
				<view class="wd-ll">
					<view>99</view>
					<view>粉丝</view>
				</view>
				<view class="wd-ll">
					<view>100</view>
					<view>接单量</view>
				</view>
				<view class="wd-ll">
					<view>99%</view>
					<view>好评率</view>
				</view>
				<view class="wd-ll">
					<view>10000元</view>
					<view>收入</view>
				</view>
			</view>
			
			</uni-card>	
			<!-- <uni-list-item
				title="" 
				note="账号:123456" 
				rightText="粉丝:9999"
				thumb="../../static/images/tx.jpg"
				thumb-size="lg"
				:showArrow="false">
				<template v-slot="left">
					<view class="my-title">
						<text>张三</text>
						<text>
							<uni-tag text="vip" type="warning" :circle="true" :inverted="true":display="true" class="my-vip" ></uni-tag>
						</text>
					</view>
				</template>
			</uni-list-item> -->
			<uni-list-item  title="会员成长" />
			<uni-list-item  title="我的资产" />
			<uni-list-item  title="我的客服" />
			<uni-list-item  title="帮助与反馈" />
			<uni-list-item  title="退出" @click="tc" />
		</uni-list>
	</view>
</template>

<script>
	import uniList from '@/components/uni-list/uni-list.vue'
	import uniListItem from '@/components/uni-list-item/uni-list-item.vue'
	import uniTag from "@/components/uni-tag/uni-tag.vue"
	import uniCard from '@/components/uni-card/uni-card.vue'
	
	export default {
		components: {uniList, uniListItem, uniTag, uniCard},
		data() {
			return {
				
			}
		},
		methods: {
			tc() {
				uni.navigateTo({
					url: '/pages/login/login'
				});
			}
		}
	}
</script>

<style>
	.wd {
		display: flex;
		justify-content: center;
		font-size: 16px;
	}
	
	.wd-ll {
		width: 100px;
		text-align: center;
	}
	
	.ic {
		width: 20px;
		height: 60px;
		line-height: 60px;
	}
	
	.grxx {
		background-color: #F4F5F6;
	}
	
	.my-title {
		display: flex;
	}
	
	.my-vip {
		margin-left: 10px;
		width: 20px;
		height: 20px;
		line-height: 20px;
		position: absolute;
		top: 20px;
		left: 87px;
	}
	
</style>
