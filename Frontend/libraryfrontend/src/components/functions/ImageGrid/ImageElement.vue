<template>
	<v-card elevation="2" class="content">
		<v-img class="img" alt="Doesnt Worked!" :src="img" :aspect-ratio="16 / 9"></v-img>
		<br />
		<v-divider></v-divider>
		<h3>Your UserName</h3>
		<v-card-text align="center" class="description">
			{{ ImgDescription }}
		</v-card-text>
		<v-btn-toggle v-model="toggle_exclusive" class="btn_lidime">
			<v-btn>
				<v-icon>mdi-thumb-up-outline</v-icon>
			</v-btn>
			<v-btn>
				<v-icon>mdi-message-bulleted</v-icon>
			</v-btn>
			<v-btn>
				<v-icon>mdi-star-plus-outline</v-icon>
			</v-btn>
			<v-btn>
				<v-icon>mdi-thumb-down-outline</v-icon>
			</v-btn>
		</v-btn-toggle>
		<br />
	</v-card>
</template>

<script>
export default {
	name: "ImageElement",
	props: ["ImgDescription", "ImgFile"],
	data: () => ({
		source: "http://127.0.0.1:8000/backend",
		img: "",
		toggle_exclusive: undefined,
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
	width: 100%;
}
.btn_lidime {
	margin-left: 13%;
}
</style>
