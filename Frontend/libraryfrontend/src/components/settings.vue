<template>
	<div>
		<v-overlay :z-index="zIndex" :value="overlay">
			<v-card class="settings">
				<h1 class="text-center">That's your settings!</h1>
			</v-card>
			<br />
			<v-btn class="white--text" color="deep-purple darken-3" @click="overlay = false">
				<v-icon dark left> mdi-arrow-left </v-icon>Back</v-btn
			>
		</v-overlay>
		
	</div>
</template>

<script>
export default {
	data: () => ({
		overlay: true,
		zIndex: 3,
	}),
};
</script>

<style>
	.settings{
		width: 500px;
		height: 250px;
	}
</style>
