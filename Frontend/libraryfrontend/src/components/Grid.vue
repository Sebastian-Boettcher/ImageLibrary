<template>
	<v-row>
		<v-col v-for="n in 9" :key="n" class="d-flex child-flex test" cols="4">
			<v-img
				:src="`https://picsum.photos/500/300?image=${n * 5 + 10}`"
				:lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}`"
				aspect-ratio="1"
				class="grey lighten-2 test"
			>
				<template v-slot:placeholder>
					<v-row class="test ma-0" align="center" justify="center">
						<v-progress-circular indeterminate color="grey lighten-5"></v-progress-circular>
					</v-row>
				</template>
			</v-img>
		</v-col>
	</v-row>
</template>

<script>
export default {
	name: "Grid",
};
</script>

<style>

</style>
