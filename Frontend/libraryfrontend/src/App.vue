<template>
	<v-app color="lime lighten-5">
		<layout />
		
	</v-app>
</template>


<script>
import layout from "./components/layout.vue";
export default {
	name: "App",

	components: {
		layout,
	},

	data: () => ({
		//
	}),
};
</script>
