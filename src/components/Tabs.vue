<template>
	<div>
		<div class="tabs is-centered is-boxed">
			<ul>
				<li  v-for="tab in tabs" :class="{'is-active': tab.isActive}">
					<a :href="tab.href" @click="selectTab(tab)">
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
	export default {
		data() {
			return {
				tabs:[]
			}
		},

		created() {
			this.tabs = this.$children;
		},

		methods: {
			selectTab(selectedTab) {
				this.tabs.forEach(tab => {
					tab.isActive = (tab.name == selectedTab.name)
				});
			}
		}
	}
</script>