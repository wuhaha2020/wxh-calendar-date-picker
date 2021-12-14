### 安装方式
本组件符合[easycom]规范，`HBuilderX 2.5.5`起，只需将本组件导入项目，在页面`template`中即可直接使用，无需在页面中`import`和注册`components`。

#### 用法 
```html
<template>
	<view class="content">
		<button @click="open">Open Calendar</button>
		<wxh-calendar-date-picker ref="datePiker" 
			@pickSuccess="pickSuccess"   
			title="日期选择器" 
			:holidays="holidays" 
			:weekendCanPick="true" 
			:holidayCanPick="true" 
			:lostdayCanPick="false"
			:beginDate="beginDate"
			:maxMonth="6"/>
		<text>date:{{date}}</text>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				date: null, //选择日期
				holidays:['2021-12-12','2022-1-1','2022-2-14','2022-5-1','2022-9-10','2022-10-1'], //休息日数组
				beginDate: new Date() , //最早可选日期为当前日期
			}
		},
		methods: {
			open(){
				this.$refs.datePiker.show();
			},
			pickSuccess(date){
				this.date = date
			}
		}
	}
</script>
```

## API

### 属性

|属性名					|类型		|默认值		|说明																																														|
|:-:					|:-:		|:-:		|:-:																																														|
|title					|String		|日期选择			|显示组件的标题|																																												|
|holidays			|Array		|[]		|休息日期数组|
|weekendCanPick					|Boolean		|false			|周六日是否可选|
|holidayCanPick					|Boolean		|false			|休息日是否可选|
|lostdayCanPick					|Boolean		|false			|已过日期是否可选|
|beginDate					|String		|无			|最早可选日期|
|maxMonth					|Number		|6			|显示月份总数|

### 方法
|函数名					|返回参数				|说明																																														|
|:-:					|:-:				|:-:																																														|
|@pickSuccess					|date(YYYY-MM-DD)			|返回选择的日期|


