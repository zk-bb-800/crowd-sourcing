<template>
	<view class="ydy2-list">
		
		<uni-tag text="视频制作" type="warning" :circle="true" :inverted="true" class="list-tag" @click="bindClick"></uni-tag>
		<uni-tag text="平面设计" type="error" :circle="true" :inverted="true" class="list-tag"></uni-tag>
		<uni-tag text="photoShop" type="primary" :circle="true" :inverted="true" class="list-tag"></uni-tag>
		<uni-tag text="logo设计" type="success" :circle="true" :inverted="true" class="list-tag"></uni-tag>
		
		<uni-tag text="视频编辑" type="warning" :circle="true" :inverted="true" class="list-tag"></uni-tag>
		<uni-tag text="影视特效" type="error" :circle="true" :inverted="true" class="list-tag"></uni-tag>
		<uni-tag text="3D动画" type="primary" :circle="true" :inverted="true" class="list-tag"></uni-tag>
		<uni-tag text="技能" type="success" :circle="true" :inverted="true" class="list-tag"></uni-tag>
		
		<uni-tag text="技能" type="warning" :circle="true" :inverted="true" class="list-tag"></uni-tag>
		<uni-tag text="技能" type="error" :circle="true" :inverted="true" class="list-tag"></uni-tag>
		<uni-tag text="技能" type="primary" :circle="true" :inverted="true" class="list-tag"></uni-tag>
		<uni-tag text="技能" type="success" :circle="true" :inverted="true" class="list-tag"></uni-tag>
		
		<uni-tag text="技能" type="warning" :circle="true" :inverted="true" class="list-tag"></uni-tag>
		<uni-tag text="技能" type="error" :circle="true" :inverted="true" class="list-tag"></uni-tag>
		<uni-tag text="技能" type="primary" :circle="true" :inverted="true" class="list-tag"></uni-tag>
		<uni-tag text="技能" type="success" :circle="true" :inverted="true" class="list-tag"></uni-tag>
		
	</view>
</template>

<script>
	import uniTag from "@/components/uni-tag/uni-tag.vue"
	
	export default {
		components: {uniTag},
		data() {
			return {
				
			}
		},
		methods: {
			bindClick() {
				uni.switchTab({
					url:'../list/list'
				})
			}
		}
	}
</script>

<style>
	
	.ydy2-list {
		margin-top: 20px;
		display: flex;
		flex-wrap: wrap;
	}
	
	.list-tag {
		width: 80px;
		margin: 5px;
		height: 40px;
		line-height: 40px;
		border-radius: 50px;
	}
</style>
