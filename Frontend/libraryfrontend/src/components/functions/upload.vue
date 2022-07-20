<template>
	<div>
		<v-card class="card">
			<v-card-title class="justify-center title">Upload your photos</v-card-title>
			<v-file-input
				placeholder="Select Image"
				counter
				multiple
				accept="image/png, image/jpeg"
				prepend-icon="mdi-camera"
				v-model="selectedFile"
			></v-file-input>
			<v-text-field label="Description" v-model="description" hide-details="auto"></v-text-field>
			<br />
			<v-btn block elevation="2" color="deep-purple darken-2" @click="uploadFile"
				>Upload <v-icon right dark> mdi-cloud-upload </v-icon></v-btn
			>
		</v-card>
		<br />
	</div>
</template>

<script>
import axios from "axios";
export default {
	data: () => ({
		overlayUpload: true,
		zIndex: 2,
		description: "",
		selectedFile: null,
		title: "",
		src: "",
		files: null,
	}),
	methods: {
		uploadFile() {
			console.log(this.selectedFile[0].name)
			let data = {
				description: this.description,
				img: this.selectedFile[0],
			};
			this.description = '';
			this.selectedFile = null;

			axios
				.post("http://localhost:8000/backend/upload_image/", data, {
					headers: {
						"Content-Type": "multipart/form-data",
					},
				})
				.then((response) => {
					console.log(response);
				});
		},
	},
};
</script>

<style>
.card {
	width: 500px;
	padding: 18px;
	height: 300px;
}
.title {
	text-transform: uppercase;
}
.background {
	color: #4dd0e1;
}
</style>
