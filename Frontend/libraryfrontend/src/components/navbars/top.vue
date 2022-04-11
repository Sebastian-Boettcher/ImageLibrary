<template>
	<div>
		<v-toolbar dense elevation="9" color="deep-purple darken-3">
			<v-btn icon>
				<v-icon color="white" @click="toggleUpload">mdi-plus</v-icon>
			</v-btn>
			<v-spacer></v-spacer>
			<v-toolbar-title class="ml-16 title">Image Booth</v-toolbar-title>

			<v-spacer></v-spacer>

			<v-btn icon>
				<v-icon color="white" @click="toggleSettings">mdi-dots-vertical</v-icon>
			</v-btn>
		</v-toolbar>

		<v-overlay :z-index="zIndex1" :value="Upload" class="background" v-if="Upload">
			<upload />
			<v-btn class="black--text" color="cyan lighten-2" @click="Upload = false">
				<v-icon dark left> mdi-arrow-left </v-icon>Back</v-btn
			>
		</v-overlay>

		<settings v-if="Settings" />
	</div>
</template>

<script>
import upload from "../upload.vue";
import settings from "../settings.vue";
export default {
	components: {
		upload,
		settings,
	},
	data: () => ({
		Upload: false,
		Settings: false,
		zIndex2: 2,
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

<style></style>
