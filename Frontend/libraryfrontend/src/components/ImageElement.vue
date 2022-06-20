<template>
	<v-card elevation="2" class="content">
		<!--<v-img class="profil" src="#">Profilpic</v-img>
        <v-card-title class="user">User Name</v-card-title>-->
		<v-img class="img" alt="Doesnt Worked!" src="./Blank.png"></v-img>
		<v-card-text align="center" class="description">
			{{ ImgDescription }}
		</v-card-text>
	</v-card>
</template>

<script>
export default {
	name: "ImageElement",
	props: ["ImgDescription", "ImgFile"],
	data: () => ({

	}),
	methods: {},
};
</script>

<style>
    .content{
        width: 250px;
		padding: 5px;
		margin-top: 50px;
    }
	.img{
		width: 150px;
		height: auto;
		display: block;
		margin-left: auto;
		margin-right: auto;
		width: 50%;
	}
</style>
