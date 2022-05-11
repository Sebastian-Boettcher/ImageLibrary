<template>
	<div>
		<v-card class="card">
			<v-card-title class="justify-center title">Upload your photos</v-card-title>
			<v-text-field label="Image Title" :rules="rules" hide-details="auto"></v-text-field>
			<v-text-field label="Description"></v-text-field>
			<v-file-input counter multiple  prepend-icon="mdi-camera" :filename="filename"></v-file-input>
			<p>{{  file_name }}</p>
		</v-card>
		<br />
		
	</div>
</template>

<script>
import axios from "axios";
export default {
	//props: ['overlayUpload'],
	data: () => ({
		overlayUpload: true,
		zIndex: 2,
		title: "",
		description: "",
		file_name: "",
		rules: [(value) => !!value || "Required.", (value) => (value && value.length <= 140) || "To Many Charakters"],
	}),
	methods: {
		async upload() {
			let data = {
				title: this.title,
				Description: this.description,
				File_name: this.filename,
			};
			let json = JSON.stringify(data);
			let config = {
				headers: {
					"Content-Type": "application/json",
				},
			};
			await axios.post("http://localhost:8000/backend/upload/", json, config).then((response) => {console.log(response)}) 
		},
		fileOutput(){
			print(this.filename)
		}
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
