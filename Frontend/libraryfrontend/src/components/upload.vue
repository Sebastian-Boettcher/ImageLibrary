<template>
	<div>
		<v-card class="card">
			<v-card-title class="justify-center title">Upload your photos</v-card-title>
			<v-file-input counter multiple show-size truncate-length="21"></v-file-input>
		</v-card>
		<br />
	</div>
</template>

<script>
export default {
	//props: ['overlayUpload'],
	data: () => ({
		overlayUpload: true,
		zIndex: 2,
	}),
};
</script>

<style>
.card {
	width: 500px;
	padding: 18px;
	height: 200px;
}
.title {
	text-transform: uppercase;
}
.background {
	color: #4dd0e1;
}
</style>
