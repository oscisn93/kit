<script>
	export let data;
	console.log(data)
	const types = data.types.map(type=>type.type.name);
	console.log(types);
	const color = {
        grass: "bg-green-600 text-white font-bold px-1 rounded-md",
        poison: "bg-purple-700 text-white font-bold px-1 rounded-md",
        water: "bg-blue-500 text-white font-bold px-1 rounded-md",
        fairy: "bg-pink-400 text-white font-bold px-1 rounded-md",
        electric: "bg-yellow-300 text-white font-bold px-1 rounded-md",
		fire: "bg-orange-600 text-white font-bold px-1 rounded-md",
		flying: "bg-blue-200 text-white font-bold px-1 rounded-md",
		bug: "bg-lime-600 text-white font-bold px-1 rounded-md",
		normal: "bg-gray-200 text-white font-bold px-1 rounded-md",
		ground: "bg-yellow-800 text-white font-bold px-1 rounded-md",
		fighting: "bg-rose-800 text-white font-bold px-1 rounded-md",
		psychic: "bg-pink-600 text-white font-bold px-1 rounded-md",
		rock: "bg-orange-900 text-white font-bold px-1 rounded-md",
		steel: "bg-gray-400 text-white font-bold px-1 rounded-md",
		ghost: "bg-violet-900 text-white font-bold px-1 rounded-md",
		ice: "bg-teal-200 text-white font-bold px-1 rounded-md",
		dragon: "bg-indigo-500 text-white font-bold px-1 rounded-md",
    };
	function classNames(...classes) {
		return classes.join();
	}
</script>

<div class="flex flex-col items-center">
	<h1 class="text-4xl text-center my-8 uppercase">
		{data.name}
	</h1>
	<p>
		Type: 
		{#each types as type}
			<span class={color[type]}>{type} </span>
		{/each}
		| Height: <strong>{data.height}</strong> | Weight:
		<strong>{data.weight}</strong>
	</p>
	<img class="h-48 w-48" src={data.sprites['front_default']} alt={data.name} />
</div>
