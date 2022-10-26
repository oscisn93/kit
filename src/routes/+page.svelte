<script>
	export let data;
	import PokemanCard from '../components/PokemanCard.svelte';

	let searchTerm = '';
	let filteredPokemon = [];

	$: {
		if (searchTerm) {
			filteredPokemon = data.props.filter((pokemon) =>
				pokemon.name.toLowerCase().includes(searchTerm.toLowerCase())
			);
		} else {
			filteredPokemon = [...data.props];
		}
	}
</script>

<svelte:head>
	<title>Svelte Kit Pokedex</title>
</svelte:head>

<h1 class="test-4xl text-center my-8 uppercase">Svelte Kit Pokedex</h1>

<input
	class="w-8/12 rounded-md text-lg p-4 border-2 border-gray-200"
	type="text"
	bind:value={searchTerm}
	placeholder="Search Pokemon"
/>
<div class="lg:px-10 py-4 grid gap-4 lg:grid-cols-3 md:grid-cols-2 grid-cols-1">
	{#each filteredPokemon as pokeman}
		<PokemanCard {pokeman} />
	{/each}
</div>
