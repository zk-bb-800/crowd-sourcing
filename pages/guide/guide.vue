<template>
	<view class="ydy1-list">
		<navigator url="../guide2/guide2">
			<uni-tag text="设计类" type="warning" :circle="true" :inverted="true" class="list-tag"></uni-tag>
		</navigator>
		<uni-tag text="文案类" type="success" :circle="true" :inverted="true" class="list-tag"></uni-tag>
		<uni-tag text="IT类" type="primary" :circle="true" :inverted="true" class="list-tag"></uni-tag>
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
			
		}
	}
</script>

<style>
	
	.ydy1-list {
		margin: 150px 10px 0 10px;
		text-align: center;
	}
	
	.list-tag {
		width: 300px;
		height: 45px;
		line-height: 45px;
		margin: 50px auto;
		border-radius: 50px;
	}
</style>
