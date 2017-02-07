<template>
	<div class="modal is-active">
		<div class="modal-background"></div>
		<div class="modal-content">
			<div class="box">
				<slot></slot>
			</div>
		</div>
		<button class="modal-close" @click="$emit('close')"></button>
	</div>
</template>

<style></style>

<script>
	export default {
		name:'modal',
		data() {
			return {}
		}
	}
</script>