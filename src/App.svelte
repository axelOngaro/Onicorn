<script>
	import Drink from "./components/Drink.svelte"
	async function fetchApi(){
	const response = await fetch("https://www.thecocktaildb.com/api/json/v1/1/search.php?s=margarita")
	const cocktails = await response.json();
	return cocktails
	}

	let promise = fetchApi()
	
	</script>
	
	<svelte:head>
		<!-- Le CDN de tailwind pour utiliser la librairie :  https://tailwindcss.com -->
		<link
			href="https://unpkg.com/tailwindcss@^2/dist/tailwind.min.css"
			rel="stylesheet"
		/>
	</svelte:head>
	
	<h1 class="relative w-full bg-blue-500 text-center font-extrabold text-5xl p-4 mb-8 ">The margarita collection</h1>
	<div class="flex flex-wrap h-1/4 absolute gap-4 justify-center ">
		
		{#await promise}
			<p>... wating for data</p>
		{:then {drinks} } 
			{#each drinks as drink}
				<Drink {...drink} />
			{/each}
		{/await}
	</div>
	