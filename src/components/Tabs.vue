<template>
	<div>
		<div class="tabs is-centered is-boxed">
			<ul>
				<li  v-for="tab in tabs">
					<a href="#">
						<span>{{tab.name}}</span>
					</a>
				</li>
			</ul>
		</div>

		<div class="tab-content">
			<slot></slot>
		</div>

	</div>
</template>

<style></style>

<script>
import Tab from './Tab';
	export default {
		data() {
			return {
				tabs:[]
			}
		},
		created() {
			this.tabs = this.$children;
		}
	}
</script>