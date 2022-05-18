<template>
	<div>
		<top />
		<v-row justify="center" class="gallery">
			<v-btn class="white--text" color="deep-purple darken-3" @click="overlay = !overlay"> Show Images </v-btn>
			<v-overlay :z-index="zIndex" :value="overlay">
				<grid />
				<br />
				<v-btn class="white--text" color="deep-purple darken-3" @click="overlay = false">
					<v-icon dark left> mdi-arrow-left </v-icon>Back</v-btn
				>
			</v-overlay>
		</v-row>
		<bottom class="bottom" />
	</div>
</template>

<script>
import Grid from "./Grid.vue";
import bottom from "./navbars/bottom.vue";
import top from "./navbars/top.vue";
import axios from "axios";

export default {
	components: {
		Grid,
		bottom,
		top,
		images: {},
	},
	data: () => ({
		overlay: false,
		zIndex: 0,
	}),
	methods: {
		async grid() {
			let config = {
				headers: {
					"Content-Type": "application/json",
				},
			};
			await axios.get("http://localhost:8000/backend/grid/").then((response) => {
				console.log(response.data);
			});
		},
	},
};
</script>

<style>
.bottom {
	margin-top: 43.1%;
	position: fixed;
}
.gallery {
	margin-top: 18%;
}
.title {
	color: white;
	text-transform: uppercase;
}
</style>
