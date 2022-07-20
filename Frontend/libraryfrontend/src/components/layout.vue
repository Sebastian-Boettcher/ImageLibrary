<template>
	<div class="background">
		<top />

		<SideBar class="fix"/>

		<grid :testData="data" class="grid ml-11 pa-2 mb-1" />

		<bottom class="bottom pa-1" />
	</div>
</template>

<script>
import Grid from "./functions/ImageGrid/Grid.vue";
import bottom from "./navbars/bottom.vue";
import top from "./navbars/top.vue";
import SideBar from "./navbars/SideBar.vue";

import axios from "axios";

export default {
	components: {
		Grid,
		SideBar,
		bottom,
		top,
		images: {},
	},
	data: () => ({
		hide: true,
		opacity: 0,
		data: "",
		closeOnContentClick: false,
		items: [{ title: "Click Me" }, { title: "Click Me" }, { title: "Click Me" }, { title: "Click Me 2" }],
	}),
	methods: {
		async getData() {
			this.overlay = !this.overlay;
			this.hide = !this.hide;

			await axios.get("http://localhost:8000/backend/grid/").then((response) => {
				console.log(response.data);
				this.data = response.data;
			});
		},
		toggle() {
			this.overlay = !this.overlay;
			this.hide = !this.hide;
		},
	},
	mounted() {
		this.getData();
	},
};
</script>

<style>
.bottom {
	z-index: 0;
	position: fixed;
	width: 100%;
	height: auto;
}
.title {
	color: white;
	text-transform: uppercase;
}
.sideMenu {
	width: 2.9%;
}
:hover .sideMenu {
	width: 10%;
}
.fix{
	position: fixed;
	z-index: 1;
}
.background{
	background-color:#EEEEEE ;
}
.grid{
	z-index: 0;
}
</style>
