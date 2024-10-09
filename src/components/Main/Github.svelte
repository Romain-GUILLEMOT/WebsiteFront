<script>
	import { onMount } from 'svelte';

	let repositories = [];
	let selectedUser = 'Romain-GUILLEMOT';

	// Fetch the repositories from GitHub API
	async function fetchRepos(username) {
		selectedUser = username;
		const response = await fetch(`https://api.github.com/users/${username}/repos`);
		repositories = await response.json();
	}

	// Event listener for button click
	onMount(() => {
		// Fetch Romain-GUILLEMOT repos by default
		fetchRepos('Romain-GUILLEMOT');
	});
</script>

<!-- Affichage des dépôts -->
<div class="w-full bg-gray-100 py-12">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div class="text-center mb-10">
			<h2 id="category-heading" class="text-3xl font-bold tracking-tight text-gray-900">Mes dépôts GitHub</h2>
			<p class="text-lg text-gray-600">Liste des projets disponibles sur mon GitHub.</p>
		</div>
		<div class="flex justify-center mb-6">
			<button
				id="romain-button"
				class="mx-2 py-2 px-4 font-semibold rounded-lg shadow-md focus:outline-none
					{selectedUser === 'Romain-GUILLEMOT' ? 'bg-blue-500 text-white' : 'bg-gray-200 text-gray-800 hover:bg-gray-300'}"
				on:click={() => fetchRepos('Romain-GUILLEMOT')}
			>
				Dépôts de Romain-GUILLEMOT
			</button>
			<button
				id="bagou-button"
				class="mx-2 py-2 px-4 font-semibold rounded-lg shadow-md focus:outline-none
					{selectedUser === 'Bagou4502' ? 'bg-blue-500 text-white' : 'bg-gray-200 text-gray-800 hover:bg-gray-300'}"
				on:click={() => fetchRepos('Bagou4502')}
			>
				Dépôts de Bagou450
			</button>
		</div>
		<p class="text-center opacity-50 my-4"> Il est à noter que tous les dépôts de Bagou450 ont été entièrement développés par Romain GUILLEMOT et simplement hébergés sur le compte GitHub de l'entreprise.</p>
		<div id="repos-container" class="grid grid-cols-1 gap-6 sm:grid-cols-2 lg:grid-cols-3">
			<!-- Les dépôts seront rendus ici -->
			{#each repositories as repo}
				<div class="group relative bg-white rounded-lg shadow-lg overflow-hidden p-6 transform transition duration-300 hover:scale-105 hover:shadow-xl">
					<div class="flex items-center justify-between mb-4">
						<span class="inline-flex rounded-full bg-indigo-100 p-3 text-indigo-700 ring-4 ring-white">
							{#if repo.archived}
								<svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true">
									<path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7" />
								</svg>
							{:else}
								<svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true">
									<path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6h4.5m4.5 0a9 9 0 1 1-18 0 9 9 0 0 1 18 0Z" />
								</svg>
							{/if}
						</span>
					</div>
					<div class="mt-4">
						<h3 class="text-lg font-semibold text-gray-900 mb-2">
							<a href="{repo.html_url}" target="_blank" class="focus:outline-none">
								<span class="absolute inset-0" aria-hidden="true"></span>
								{repo.name}
								{#if repo.archived}
									<span class="inline-block bg-yellow-100 text-yellow-800 text-xs font-semibold mr-2 px-2.5 rounded">Archivé</span>
								{:else}
									<span class="inline-block bg-green-100 text-green-800 text-xs font-semibold mr-2 px-2.5 rounded">En cours</span>
								{/if}
							</a>
						</h3>
						<p class="text-sm text-gray-500">{repo.description || "Aucune description disponible."}</p>
					</div>
				</div>
			{/each}
		</div>
	</div>

</div>