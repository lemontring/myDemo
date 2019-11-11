<template>
	<view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		props:["msg"],
		methods:{
				
			test(){
				this.$emit("testShowName")
			}
		}
	}
</script>

<style lang="scss">

</style>
