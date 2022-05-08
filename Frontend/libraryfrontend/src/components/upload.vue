<template>
	<div>
		<v-card class="card">
			<v-card-title class="justify-center title">Upload your photos</v-card-title>
			<v-text-field label="Image Title" :rules="rules" hide-details="auto"></v-text-field>
			<v-text-field label="Description"></v-text-field>
			<v-file-input counter multiple show-size truncate-length="21"></v-file-input>
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
		upload() {
			data = {
				Title: this.title,
				Description: this.description,
				File_name: this.file_name,
			};
			axios({
				method: "post",
				url: "http://127.0.0.1:8000/",
			}).then((response) => (data = response.data));
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
