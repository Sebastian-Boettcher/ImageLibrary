<template>
	<div class="top">
		<v-toolbar dense elevation="9" color="deep-purple accent-4">
			<v-toolbar-title class="ml-16 title">Image Booth</v-toolbar-title>

			<v-spacer></v-spacer>

			<v-btn icon @click="toggleUpload">
				<v-icon color="white">mdi-dots-vertical</v-icon>
			</v-btn>
		</v-toolbar>

		<v-bottom-sheet :value="Upload" class="overlay" v-model="Upload" inset>
			<!--<v-sheet class="text-center">
				<h1 class="mt-12">Hey</h1>
				
			</v-sheet>-->
			<upload class="testing " />
		</v-bottom-sheet>
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
