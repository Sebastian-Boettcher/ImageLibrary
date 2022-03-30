<template>
	<div>
		<v-toolbar dense elevation="9" color="deep-purple darken-3">
			<v-spacer></v-spacer>
			<v-toolbar-title class="ml-16 title">Image Booth</v-toolbar-title>

			<v-spacer></v-spacer>

			<v-btn icon>
				<v-icon color="white">mdi-magnify</v-icon>
			</v-btn>

			<v-btn icon>
				<v-icon color="white">mdi-dots-vertical</v-icon>
			</v-btn>
		</v-toolbar>

		<v-row justify="center" class="gallery">
			<v-btn class="white--text" color="deep-purple darken-3" @click="overlay = !overlay"> Show Images </v-btn>

			<v-overlay :z-index="zIndex" :value="overlay">
				<grid />
				<br>
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
import bottom from "./bottom.vue";

export default {
	components: {
		Grid,
		bottom,
	},

	data: () => ({
		overlay: false,
		zIndex: 0,
	}),
};
</script>

<style>
	.bottom{
		margin-top: 43.1%;
		position: fixed;
	}
	.gallery{
		margin-top: 18%;
	}
	.title{
		color: white;
		text-transform: uppercase;

	}
</style>
