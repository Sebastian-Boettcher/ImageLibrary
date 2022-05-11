<template>
	<v-row>
		<v-col v-for="n in 9" :key="n" class="d-flex child-flex test" cols="4">
			<v-img
				:src="`https://picsum.photos/500/300?image=${n * 5 + 10}`"
				:lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}`"
				aspect-ratio="1"
				class="grey lighten-2"
				height="230px"
				width="115px"
			>
				<template v-slot:placeholder>
					<v-row class="ma-0" align="center" justify="center">
						<v-progress-circular indeterminate color="deep-purple darken-3"></v-progress-circular>
					</v-row>
				</template>
			</v-img>
		</v-col>
	</v-row>
</template>

<script>
import axios from "axios";
export default {
	name: "Grid",
	data: () => ({
		overlayUpload: true,
		zIndex: 2,
		data: [],
	}),
	methods: {
		async grid() {
			//let data = {};

			let config = {
				headers: {
					"Content-Type": "application/json",
				},
			};
			await axios.get("http://localhost:8000/backend/grid/", json, config).then((response) => {
				console.log(response.data);
				this.data = response.data;
				console.log(this.data)
			});
		},
	},
};
</script>

<style></style>
