<template>
	<view>
		<uni-notice-bar single="true" text="这是通告栏，成为会员balabalabalabalabalabala..."></uni-notice-bar>
		<view class="ss">
			<uni-fav
				:checked="checked" 
				class="favBtn sc" 
				circle="true" 
				bg-color="#eeeeee" 
				bg-color-checked="#007aff" 
				@click="onClick">
			</uni-fav>
		</view>
		<uni-list class="list-bj">
			<uni-list-item 
				title=""
				rightText="" 
				:showArrow="false">
				<template v-slot="left">
					<text class="list-title">ps毕业照</text>
				</template>
				<template v-slot:right>
					<text class="list-title-right">已有6位设计师投标</text>
				</template>
			</uni-list-item>
			<uni-list-item  
				title="" 
				rightText="查看个人主页">
				<template v-slot="left">
					<view>
						<text>发布人:</text>
						<text class="list-label">xx</text>
					</view>
				</template>
			</uni-list-item>
			<uni-list-item
				title="" 
				:showArrow="false">
				<template v-slot="left">
					<view>
						<text>发布时间:</text>
						<text class="list-label">8.10</text>
					</view>
				</template>
			</uni-list-item>
			<uni-list-item
				title="" 
				:showArrow="false">
				<template v-slot="left">
					<view>
						<text>预约完成时间:</text>
						<text class="list-label">8.27</text>
					</view>
				</template>
			</uni-list-item>
			<uni-list-item
				title="" 
				:showArrow="false">
				<template v-slot="left">
					<view>
						<text>需求预算:</text>
						<text class="list-label">500元以下</text>
					</view>
				</template>
			</uni-list-item>
			<uni-list-item
				title="" 
				:showArrow="false">
				<template v-slot="left">
					<view>
						<text>需求详情:</text>
						<text class="list-label">有一组团队毕业照方案方案方案方案方案方案方案方案方案方案方案方案方案方案.....</text>
					</view>
				</template>
			</uni-list-item>
		</uni-list>
		<view class="list-button">
			<button type="primary" plain="true">在线沟通</button>
			<button type="primary" plain="true" @click="sss">立即投标</button>
		</view>		
	</view>
</template>

<script>
	import uniNoticeBar from '@/components/uni-notice-bar/uni-notice-bar.vue'
	import uniList from '@/components/uni-list/uni-list.vue'
	import uniListItem from '@/components/uni-list-item/uni-list-item.vue'
	import uniFav from '@/components/uni-fav/uni-fav.vue'


	export default {
		components: {uniNoticeBar, uniList, uniListItem, uniFav},
		data() {
			return {
				checked:false
			}
		},
		methods: {
			onClick() {
				this.checked = !this.checked;
			},
			sss() {
				console.log('sss')
			}
		}
	}
</script>

<style>
.list-bj {
	background-color: #F4F5F6;
}
	
.ss {
	display: block;
	height: 30px;
}
	
.sc {
	float: right;
}
	
.list-title {
	font-size: 25px;
}

.list-title-right {
	font-size: 14px;
	color: red;
}
	
.list-label{
	color: #3c3c3c;
	margin-left: 10px;
	font-size: 17px;
}

.list-button {
	margin-top: 50px;
	display: flex;
}
</style>
