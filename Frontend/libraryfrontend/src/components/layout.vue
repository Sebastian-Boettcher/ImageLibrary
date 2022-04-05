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


export default {
	components: {
		Grid,
		bottom,
		top,
	},
	data: () => ({
		overlay: false,
		zIndex: 0,
		up_visible: false,
		set_visible: false
	}),
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
