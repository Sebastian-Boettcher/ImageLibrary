<template>
	<v-card class="mx-auto settings" height="400" width="256">
		<v-card-title class="card-title">Apps and Settings</v-card-title>
		<v-navigation-drawer class="deep-purple accent-4" dark permanent>
			<v-list>
				<v-list-item v-for="item in items" :key="item.title" link>
					<v-list-item-icon>
						<v-icon>{{ item.icon }}</v-icon>
					</v-list-item-icon>

					<v-list-item-content>
						<v-list-item-title>{{ item.title }}</v-list-item-title>
					</v-list-item-content>
				</v-list-item>
			</v-list>

			<template v-slot:append>
				<div class="pa-2">
					<v-btn block> Logout </v-btn>
				</div>
			</template>
		</v-navigation-drawer>
	</v-card>
</template>

<script>
export default {
	data() {
		return {
			items: [
				{ title: "Messenger", icon: "mdi-message-text" },
				{ title: "Account", icon: "mdi-account-box" },
				{ title: "Settings", icon: "mdi-wrench" },
			],
		};
	},
};
</script>

<style>
	.settings{
		position: fixed;
		left: 86.5%;
	}
	.card-title{
		text-align: center;
	}
</style>
