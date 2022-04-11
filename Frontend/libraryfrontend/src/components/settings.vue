<template>
	<div>
		<v-overlay :z-index="zIndex" :value="overlaySettings">
			<v-card class="settings">
				<h1 class="text-center">That's your settings!</h1>
			</v-card>
			<br />
			<v-btn class="black--text" color="cyan lighten-3" @click="overlaySettings = false">
				<v-icon dark left> mdi-arrow-left </v-icon>Back</v-btn
			>
		</v-overlay>
		
	</div>
</template>

<script>
export default {
	props: ['overlaySettings'],
	data: () => ({
		zIndex: 3,
		opacity: 10,
	}),
};
</script>

<style>
	.settings{
		width: 500px;
		height: 250px;
	}
</style>
