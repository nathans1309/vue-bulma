<template>
	<table class="table">
		<thead>
			<tr>
				<th v-for="key in keys">
					{{key}}
					<input type="text" :name="key+'-filter'" @keyup="updateFilter(key,$event.target.value)">
				</th>
			</tr>
		</thead>
		<tbody>
			<tr v-for="item in tempData">
				<td v-for="key in keys">
					{{ item[key] }}
				</td>
			</tr>
		</tbody>
		<tfoot>
			<tr>
				
			</tr>
		</tfoot>

	</table>
</template>

<style></style>

<script>
	import Axios from 'Axios';

	// const endpoint = 'https://gist.githubusercontent.com/planetoftheweb/2c2f3b03b72a7f2ae923/raw/d0236fd0a945fdac7acd463f268bd20ebe4d766c/data.json';
	const endpoint = 'https://gist.githubusercontent.com/Miserlou/c5cd8364bf9b2420bb29/raw/2bf258763cdddd704f8ffd3ea9a3e81d25e2c6f6/cities.json';
	export default {

		data() {
			return {
				data: [],
				keys: {},
				filters: []
			}
		},

		computed: {
			tempData() {
				var temp = this.data;
				this.filters.forEach(filterItem => {
					temp = temp.filter((tempItem) => {
						const regex = new RegExp(filterItem.val, 'gi');
						return tempItem[filterItem.key].toString().match(regex);
					});
				});
				return temp;
			}
		},

		created() {
			Axios.get(endpoint)
				.then(response => response.data)
				.then(data => {
					this.data = data;
					this.keys = Object.keys(this.data[0]);
				});
		},

		methods: {
			updateFilter(key, value) {
				var index = this.filters.findIndex(filterItem => filterItem.key == key);
				if ( index >= 0 ) {
					this.filters[index].val = value;
				} else {
					this.filters.push({key: key, val: value});
				}
			}
		}

	}
</script>