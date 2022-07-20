<template>
	<div class="mt-12 sideMenu" >
		<v-navigation-drawer permanent expand-on-hover color="deep-purple accent-4">
			<v-list>
				<v-list-item class="px-2">
					<v-list-item-avatar>
						<v-img src="https://randomuser.me/api/portraits/women/85.jpg"></v-img>
					</v-list-item-avatar>
				</v-list-item>

				<v-list-item link >
					<v-list-item-content>
						<v-list-item-title class="text-h6 white--text"> Username </v-list-item-title>
						<v-list-item-subtitle class="white--text">Username@gmail.com</v-list-item-subtitle>
					</v-list-item-content>
				</v-list-item>
			</v-list>

			<v-divider></v-divider>

			<v-list nav dense>
				<v-list-item link>
					<v-list-item-icon>
						<v-icon color="lime lighten-4">mdi-folder</v-icon>
					</v-list-item-icon>
					<v-list-item-title class="white--text">My Files</v-list-item-title>
				</v-list-item>
				<v-list-item link>
					<v-list-item-icon>
						<v-icon color="lime lighten-4">mdi-account-multiple</v-icon>
					</v-list-item-icon>
					<v-list-item-title class="white--text">Shared with me</v-list-item-title>
				</v-list-item>
				<v-list-item link>
					<v-list-item-icon>
						<v-icon color="lime lighten-4">mdi-star</v-icon>
					</v-list-item-icon>
					<v-list-item-title class="white--text">Starred</v-list-item-title>
				</v-list-item>
			</v-list>
		</v-navigation-drawer>
	</div>
</template>

<script>
export default {
    name: "SideBar",
};
</script>

<style>
.sideMenu {
	width: 2.9%;
}
:hover .sideMenu {
	width: 10%;
}
</style>
