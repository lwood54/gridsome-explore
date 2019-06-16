<template>
	<div>
		<h1>Content:</h1>
		<h3>{{content}}</h3>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				activeTab: "mail",
				content: ""
			};
		},
		methods: {
			handleClicked(e) {
				this.activeTab = e;
			}
		}
	};
</script>

<style scoped>
	.tab-container {
		display: flex;
		width: 100%;
		justify-content: space-around;
	}

	.tab {
		cursor: pointer;
		background-color: rgb(164, 166, 170);
		color: rgb(85, 82, 82);
		padding: 16px;
		border-radius: 4px;
	}

	.tab-active {
		background-color: rgb(60, 117, 201);
		color: rgb(206, 194, 194);
	}
</style>
