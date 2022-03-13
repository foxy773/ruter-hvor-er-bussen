<template>
	<Map />
	<button class="button" @click="getData()">Get started</button>
</template>

<script>
import Map from "../components/Map.vue";
import Bus from "../components/Bus.vue";

export default {
	components: {
				Map,
				Bus
			},
	data() {
		return {
			
		}
	},

	async created() {
		
	},

	methods: {
		async getData() {
        const API = `https://api.entur.io/realtime/v1/gtfs-rt/vehicle-positions?datasetId=RUT`;
		  const options = {
				headers: {
					'Content-Type': 'text/xml',
					'Accept': 'text/xml'
				},
			}
				const res = await fetch(API, options);
         	const results = await res.text();
           console.log(results)
			  
      },
		async findBus() {
			const results = this.getData()

			console.log(results)
			



		}
	},

	mounted() {
		
	}
}
</script>
<style>
	.button {
		position: absolute;
		top: 50%;
		left: 50%;
	}
</style>

