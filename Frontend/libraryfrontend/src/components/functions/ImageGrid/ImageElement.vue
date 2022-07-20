<template>
	<v-card elevation="2" class="content">
		<v-img class="img" alt="Doesnt Worked!" :src="img" :aspect-ratio="4/3"></v-img>
		<br />
		<v-divider></v-divider>
		<v-card-text align="center" class="description">
			{{ ImgDescription }}
		</v-card-text>
		<br />
		<v-divider></v-divider>
	</v-card>
</template>

<script>
export default {
	name: "ImageElement",
	props: ["ImgDescription", "ImgFile"],
	data: () => ({
		source: "http://127.0.0.1:8000/backend",
		img: "",
	}),
	methods: {},
	mounted() {
		this.img = this.source + this.ImgFile;
	},
};
</script>

<style>
.content {
	width: 550px;
	padding: 5px;
	margin-top: 50px;
}
.img {
	margin-left: auto;
	margin-right: auto;
	width: 50%;
}
</style>
