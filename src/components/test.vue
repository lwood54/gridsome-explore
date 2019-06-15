<template>
	<div>
		<h1>Content:</h1>
		<h3>{{content}}</h3>
	</div>
</template>

<script>
	// /spaces/{space_id}/environments/{environment_id}/content_types/{content_type_id}?access_token={access_token}
	let query;
	const contentfulBaseAPI = process.env.CONTENTFUL_BASE_API;
	console.log(contentfulBaseAPI);
	// const space_id = "c87kqyb1kdox";
	const space_id = process.env.CONTENTFUL_SPACE_ID;
	// const environment_id = "master";
	const environment_id = process.env.CONTENTFUL_ENVIRONMENT_ID;
	const content_type_id = "quizQuestion";
	// const access_token = "S_P63NpczcCqZu4R-A4Z-zgZo07kqWRObijmm3MmsKg";
	const access_token = process.env.CONTENTFUL_ACCESS_TOKEN;

	fetch(
		// `${contentfulBaseAPI}/spaces/c87kqyb1kdox?access_token=S_P63NpczcCqZu4R-A4Z-zgZo07kqWRObijmm3MmsKg`
		`${contentfulBaseAPI}/spaces/${space_id}/environments/${environment_id}/entries?access_token=${access_token}`
	)
		.then(function(response) {
			return response.json();
		})
		.then(res => {
			console.log(res);
		});
	// .then(function(myJson) {
	// 	console.log(JSON.stringify(myJson));
	// });
	// fetch("https://cdn.contentful.com", {
	// 	method: "POST",
	// 	headers: {
	// 		"content-type": "application/json",
	// 		authorization: "Bearer S_P63NpczcCqZu4R-A4Z-zgZo07kqWRObijmm3MmsKg"
	// 	},
	// 	body: JSON.stringify({
	// 		query
	// 	})
	// })
	// 	.then(res => res.json())
	// 	.then(response => {
	// 		console.log(response);
	// 		const { data } = response;
	// 	});
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
