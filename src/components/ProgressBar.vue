<template>
<div>
	
	<progress class="progress is-info" :value="currentValue" :max="maxValue">{{percentage}}%</progress>
	<button @click="currentValue++">Update Progress</button>
</div>
</template>

<style></style>

<script>
	export default {
		props: {
			minValue: {default:0},
			maxValue: {required:true}
		},

		data() {
			return {
				currentValue: 0
			}
		},

		computed: {
			percentage() {
				return (this.currentValue/this.maxValue)*100
			}
		},

		created() {
			this.currentValue = this.minValue;
		}

	}
</script>