<template>
	<div>
		<h1>Content:</h1>
		<h3>{{content}}</h3>
	</div>
</template>

<script>
	let query;
	fetch("https://cdn.contentful.com", {
		method: "POST",
		headers: {
			"content-type": "application/json",
			authorization: "Bearer S_P63NpczcCqZu4R-A4Z-zgZo07kqWRObijmm3MmsKg"
		},
		body: JSON.stringify({
			query
		})
	})
		.then(res => res.json())
		.then(response => {
			console.log(response);
			const { data } = response;
		});
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
