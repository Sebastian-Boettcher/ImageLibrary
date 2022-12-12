<template>
	<v-app id="inspire">
		<v-navigation-drawer v-model="drawer" absolute bottom temporary>
			<!--  -->
		</v-navigation-drawer>

		<v-app-bar app color="deep-purple accent-3">
			<v-app-bar-nav-icon @click="drawer = !drawer" color="white"></v-app-bar-nav-icon>

			<v-toolbar-title color="grey lighten-5"><img src="./Logotext.png" alt="ImageBooth" /></v-toolbar-title>
			<!--TODOImage Design Update-->

			<v-spacer></v-spacer>

			<v-menu top origin="center center" transition="scale-transition">
				<template v-slot:activator="{ on, attrs }">
					<v-btn icon v-bind="attrs" v-on="on">
						<v-icon color="white">mdi-dots-vertical</v-icon>
					</v-btn>
				</template>
				<!--TODO Routing to Uploadsite -->
				<v-list color="deep-purple lighten-5">
					<v-list-item v-for="(item, i) in items" :key="i">
						<v-btn color="deep-purple accent-4" block class="white--text"
							><v-icon>{{ item.icon }}</v-icon
							>{{ item.title }}</v-btn
						>
					</v-list-item>
				</v-list>
			</v-menu>
		</v-app-bar>

		<v-main>
			<v-container>
				<v-row>
					<v-col v-for="(col, index) in data.data" :key="index" cols="2" class="d-flex child-flex">
						<ImageElement
							class="flex-grow-0 flex-shrink-2"
							:ImgDescription="data.data[index].Description"
							:ImgFile="data.data[index].Img.image"
						/>
					</v-col>
				</v-row>
			</v-container>
		</v-main>
	</v-app>
</template>

<script>
import upload from "../functions/upload.vue";
import settings from "../functions/settings.vue";
import ImageElement from "../functions/ImageGrid/ImageElement.vue";

export default {
	components: {
		upload,
		settings,
		ImageElement,
	},
	props: ["data"],
	data: () => ({
		Upload: false,
		Settings: false,
		drawer: false,
		items: [
			{ title: "Bild hochladen", icon: "mdi-file-upload-outline" },
			{ title: "Abmelden", icon: "mdi-logout" },
		],
	}),
	methods: {},
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
