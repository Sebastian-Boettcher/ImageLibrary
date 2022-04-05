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
		<upload v-if="up_visible" />
		<settings v-if="set_visible" />
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
		up_visible: false,
		set_visible: false,
	}),
	methods: {
		toggleUpload() {
			this.up_visible = !this.up_visible;
		},
		toggleSettings() {
			this.set_visible = !this.set_visible;
		},
	},
};
</script>

<style></style>
