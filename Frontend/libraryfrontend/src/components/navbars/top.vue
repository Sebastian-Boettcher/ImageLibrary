<template>
	<div class="top">
		<v-toolbar dense elevation="9" color="deep-purple accent-4">
			<v-btn icon>
				<v-icon color="white" @click="toggleUpload">mdi-plus</v-icon>
			</v-btn>
			<v-spacer></v-spacer>
			<v-toolbar-title class="ml-16 title">Image Booth</v-toolbar-title>

			<v-spacer></v-spacer>

			<v-btn icon @click="toggleSettings">
				<v-icon color="white">mdi-dots-vertical</v-icon>
			</v-btn>
		</v-toolbar>

		<!--<v-overlay :z-index="zIndex1" :value="Upload" class="background" v-if="Upload">
			<upload />
			<v-btn class="black--text" color="cyan lighten-2" @click="Upload = false">
				<v-icon dark left> mdi-arrow-left </v-icon>Back</v-btn
			>
		</v-overlay>-->

		<v-bottom-sheet :value="Upload" class="overlay" v-model="Upload">
			<v-sheet class="text-center">
				<h1 class="mt-12">Hey</h1>
				<upload class="testing" />
			</v-sheet>
		</v-bottom-sheet>

		<settings v-if="Settings" />
	</div>
</template>

<script>
import upload from "../functions/upload.vue";
import settings from "../functions/settings.vue";
export default {
	components: {
		upload,
		settings,
	},
	data: () => ({
		Upload: false,
		Settings: false,
		zIndex2: 1,
		zIndex1: 1,
	}),
	methods: {
		toggleUpload() {
			this.Upload = !this.Upload;
		},
		toggleSettings() {
			this.Settings = !this.Settings;
		},
	},
};
</script>

<style>
.top {
	position: fixed;
	width: 100%;
}
.overlay {
	background-color: transparent;
	width: 100%;
}

</style>
