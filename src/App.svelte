<script lang="ts">
	import Pad from './components/Pad/Pad.svelte';
	import PadSet from './components/PadSet/PadSet.svelte';
	export let name: string;
</script>

<main>
	<h1>Drum Machine</h1>
	<PadSet />
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>