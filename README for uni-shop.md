# uni-plate-input
适配uni-app的车牌号输入组件

## 提示
**兼容 `H5` `微信小程序` , 其他平台未测试**

## 使用

1. 引入插件的vue文件并绑定触发事件

```
<template>
	<view class="cu-form-group">
		<view class="title">车牌号</view>
		<input placeholder="请点此输入" disabled="true" @tap="plateShow=true" v-model.trim="plateNo" />
		<plate-input v-if="plateShow" :plate="plateNo" @export="setPlate" @close="plateShow=false" />
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
		methods: {
			setPlate(plate){
				if(plate.length >= 7) this.plateNo = plate
				this.plateShow = false
			}
		}
	}
</script>
```
## 参数
1. `plate` 配置默认车牌号参数

## 事件
1. `export` 设置车牌号
1. `close` 关闭弹出窗

## 样式
默认使用`Less`样式,也可以在 `uni-plate-input.vue`文件中的`style`标签里将引入样式更换成css或其他
```
<style scoped lang="less">
@import './uni-plate-input'; //引入Less
// @import './uni-plate-input.css'; //引入css
</style>
```
