<template>
	<view class="cu-form-group">
		<view class="title">车牌号</view>
		<input placeholder="请点此输入" disabled="true" @tap="plateShow=true" v-model.trim="plateNo"></input>
		<plate-input v-if="plateShow" :plate="plateNo" @export="setPlate" @close="plateShow=false"></plate-input>
	</view>
</template>

<script>
	import plateInput from '@/components/uni-plate-input/uni-plate-input.vue'
	export default {
		components: {
			plateInput
		},
		data() {
			return {
				plateNo:'',
				plateShow:false
			}
		},
		onLoad() {

		},
		methods: {
			setPlate(plate){
				if(plate.length >= 7) this.plateNo = plate
				this.plateShow = false
			}
		}
	}
</script>

<style>
	
	.cu-form-group {
		border-top: 1px solid #eee;
		border-bottom: 1px solid #eee;
		background-color: #ffffff;
		padding: 1upx 30upx;
		display: -webkit-box;
		display: -webkit-flex;
		display: -ms-flexbox;
		display: flex;
		align-items: center;
		min-height: 100upx;
		justify-content: space-between;
	}

	
	
</style>
