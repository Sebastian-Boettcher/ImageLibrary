<template>
	<v-row class="row">
		<v-col v-for="(col, index) in testData.data" :key="index" cols="2" class="d-flex child-flex" >
			<ImageElement
				class="flex-grow-0 flex-shrink-2"
				:ImgDescription="testData.data[index].Description"
				:ImgFile="testData.data[index].Img.image"
			/>
		</v-col>
	</v-row>
</template>

<script>
import ImageElement from "./ImageElement.vue";
export default {
	name: "Grid",
	props: ["testData"],
	components: {
		ImageElement,
	},
	data: () => ({
		overlayUpload: true,
		zIndex: 2,
		index: 0,
	}),
	mounted() {
		this.index = this.testData.length;
	},
};
</script>

<style></style>
