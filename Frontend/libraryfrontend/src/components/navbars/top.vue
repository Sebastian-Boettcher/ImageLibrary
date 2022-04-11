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
		<upload v-if="overlayUpload" :overlayUpload="overlayUpload"/>
				<p>{{ overlayUpload }}</p>
		<settings v-if="overlaySettings" :overlaySettings="overlaySettings"/>
				<p>{{ overlaySettings }}</p>
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
		overlayUpload: false,
		overlaySettings: false,
	}),
	methods: {
		toggleUpload() {
			this.overlayUpload = !this.overlayUpload;
		},
		toggleSettings() {
			this.overlaySettings = !this.overlaySettings;
		},
	},
};
</script>

<style></style>
