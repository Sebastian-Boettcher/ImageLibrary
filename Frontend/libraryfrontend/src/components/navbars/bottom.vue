<template>
	<v-bottom-navigation :value="value" color="blue-grey darken-4" horizontal>
		<v-btn color="deep-purple lighten-5">
			<span>Recents</span>

			<v-icon color="yellow darken-1">mdi-history</v-icon>
		</v-btn>

		<v-btn color="deep-purple lighten-5">
			<span >Favorites</span>

			<v-icon color="pink darken-3">mdi-heart</v-icon>
		</v-btn>

	</v-bottom-navigation>
</template>
<script>
export default {
	name: 'Bottom',
    data: () => ({ value: 1 }),
};
</script>
