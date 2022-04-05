<template>
	<div>
		<v-overlay :z-index="zIndex" :value="overlay" class="background">
			<v-card class="card">
				<v-card-title class="justify-center title">Upload your photos</v-card-title>
				<v-file-input counter multiple show-size truncate-length="21"></v-file-input>
			</v-card>
			<br />
			<v-btn class="black--text" color="cyan lighten-2" @click="overlay = false">
				<v-icon dark left> mdi-arrow-left </v-icon>Back</v-btn
			>
		</v-overlay>
	</div>
</template>

<script>
export default {
	data: () => ({
		overlay: true,
		zIndex: 2,
	}),
};
</script>

<style>
	.card{
		width: 500px;
		padding: 18px;
		height: 200px;
	}
	.title{
		text-transform: uppercase;
	}
	.background{
		color:#4DD0E1 ;
	}

</style>
