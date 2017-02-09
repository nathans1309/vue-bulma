<template>
<a class="button" v-bind:class="{'is-active': isActive }" @click.prevent="onClick()">
		<span><slot></slot></span>
	</a>
</template>

<style></style>

<script>
	export default {
		props: {
			selected: {default:false},
			value: ''
		},

		data() {
			return {
				isActive: false
			}
		},

		methods: {
			onClick() {
				this.$parent.selectButton(this);
			}
		},

		mounted() {
			this.isActive = this.selected;
		}
	}
</script>