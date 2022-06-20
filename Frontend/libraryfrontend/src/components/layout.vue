<template>
	<div>
		<top />
		<v-row justify="center" class="gallery">
			<v-card v-if="overlay" class="overlay" transition="fab-transition">
				<grid v-click-outside="toggle" :testData="data" />
			</v-card>
			<v-btn class="white--text button" color="deep-purple darken-3" @click="get" v-if="hide" x-large outlined>
				Open Library
			</v-btn>
		</v-row>
		<bottom class="bottom" v-if="!overlay" />
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
		hide: true,
		opacity: 0,
		data: "",
	}),
	methods: {
		async get() {
			this.overlay = !this.overlay;
			this.hide = !this.hide;

			await axios.get("http://localhost:8000/backend/grid/").then((response) => {
				console.log(response.data);
				this.data = response.data;
			});
		},
		toggle() {
			this.overlay = !this.overlay;
			this.hide = !this.hide;
		},
	},
};
</script>

<style>
.bottom {
	z-index: 1;
	margin-top: 43.1%;
	position: fixed;
}
.gallery {
	position: relative;
	margin-left: 1.8%;
	margin-top: 2%;
	z-index: 1;
}
.title {
	color: white;
	text-transform: uppercase;
}
.overlay {
	width: 80%;
	height: 45%;
	padding: 10px;
	background-color: transparent;
}
.button {
	margin-top: 15%;
}
</style>
