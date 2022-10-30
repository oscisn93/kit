<script>
	import Nav from '../components/Nav.svelte';
</script>

<div class="p-8 grid max-w-6xl mx-auto items-center">
	<Nav />
	<slot />
</div>

<style>
	@tailwind base;
	@tailwind components;
	@tailwind utilities;
</style>
