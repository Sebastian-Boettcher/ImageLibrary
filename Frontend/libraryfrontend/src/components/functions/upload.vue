<template>
	<div>
		<!--In der Ecke eine Button mit dem zwischen den Settings und den Uploads gewechselt werden kann. Default ist der Upload Component -->
		<v-card class="card" elevation="0">
			<div class="float-left w">
				<h1 class="w1">Upload</h1>
				<h1 class="w2">new</h1>
				<h1 class="w3">Images</h1>
			</div>
			<div class="inpur">
				<img :src="preview" alt="Kein Bild ausgewählt" class="preview" @click="change" :aspect-ratio="4/3"/>
				<div class="inputField float-left">
					<v-file-input
						placeholder="Select Image"
						counter
						multiple
						accept="image/png, image/jpeg"
						prepend-icon="mdi-camera"
						v-model="selectedFile"
						@change="fileChange"
					></v-file-input>
					<v-text-field label="Description" v-model="description" hide-details="auto" required></v-text-field>
					<br />
					<v-btn class="btnn" block elevation="2" color="deep-purple darken-2" @click="uploadFile"
						>Upload <v-icon right dark> mdi-cloud-upload </v-icon></v-btn
					>
				</div>
			</div>
		</v-card>
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
		preview: require('../functions/notselected.png'),
		title: "",
		src: "",
		files: null,
	}),
	methods: {
		uploadFile() {
			console.log(this.selectedFile[0].name);
			let data = {
				description: this.description,
				img: this.selectedFile[0],
			};
			this.description = "";
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
		fileChange() {
			const file = this.selectedFile[0];
			this.preview = URL.createObjectURL(file) || this.preview;
		},
		change(){
			this.preview = require('../functions/notselected.png')
		}
	},
};
</script>

<style>
.card {
	width: 100%;
	padding: 18px;
	height: 300px;
}
.w {
	margin-top: 30px;
	margin-right: 9px;
	text-transform: uppercase;
}
.w2 {
	margin-left: 80px;
	margin-top: 10px;
}
.w3 {
	margin-left: 120px;
	margin-top: 10px;
}

.preview {
	width: 370px;
	height: 300px;
	margin-top: -18px;
	margin-left: 30px;
	object-fit: cover;
}
.btnn{
	margin-top: 10%;
}
.inputField {
	width: 60%;
}
.inpur {
	margin-left: 22%;
	
}
</style>
