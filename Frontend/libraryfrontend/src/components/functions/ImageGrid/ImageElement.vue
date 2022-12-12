<template>
	<v-card elevation="1" class="content">
		<v-card-title>
			Your UserName
			<v-spacer></v-spacer>
			<v-btn value="add" elevation="0" color="white">
				<v-icon color="deep-purple lighten-4"> mdi-account-multiple-plus-outline </v-icon>
			</v-btn>
		</v-card-title>
		<v-img class="img" alt="Doesnt Worked!" :src="img" :aspect-ratio="16 / 9"></v-img>
		<v-card-text align="center" class="description">
			{{ ImgDescription }}
		</v-card-text>
		<v-card-footer>
			<v-btn-toggle class="ml-7" group>
				<v-btn value="nice">
					<v-icon large color="green accent-3"> mdi-arrow-up-bold-box-outline </v-icon>
				</v-btn>

				<v-btn value="save"> <v-icon large color="yellow accent-4"> mdi-star-plus-outline </v-icon> </v-btn>

				<v-btn value="meh">
					<v-icon large color="red accent-3"> mdi-arrow-down-bold-box-outline </v-icon>
				</v-btn>
			</v-btn-toggle>
		</v-card-footer>
	</v-card>
</template>

<script>
export default {
	name: "ImageElement",
	props: ["ImgDescription", "ImgFile"],
	data: () => ({
		source: "http://127.0.0.1:8000/backend", //TODO URL wegpacken
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
