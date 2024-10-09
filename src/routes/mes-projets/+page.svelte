
<script lang="ts">
	let modalVisible = false;
	let modalImageSrc = '';

	type TagColor = {
		bg: string;
		text: string;
	};


	function normalizeTag(tag: string) {
		return tag.normalize("NFD").replace(/[\u0300-\u036f]/g, "").toLowerCase();
	}


	function showModal(src: string) {
		modalImageSrc = src;
		modalVisible = true;
	}

	function closeModal() {
		modalVisible = false;
	}

	function onKeyDown(event: KeyboardEvent) {
		if (event.key === 'Escape') {
			closeModal();
		}
	}


	export let projects = [

		{
			image: '/img/projects/ozlaloc.png',
			name: 'Ozlaloc',
			done: false,
			description: "En tant qu'employé chez Ozlaloc (CDD jusqu'en mars 2024), je développe un nouveau site pour remplacer l'ancien fait sous WordPress. Actuellement, seule la page vitrine est disponible.",
			tags: ['Laravel', 'React', 'Gestion de Projet', 'SEO'],
			domain: 'Développement Web',
			buttons: [
				{ name: 'Visiter le site', link: 'https://ozlaloc.fr', color: 'bg-blue-600' }
			],
			source: false
		},
		{
			image: '/img/projects/bagou450.png',
			name: 'Bagou450',
			done: true,
			description: "Bagou450, mon ancienne entreprise, proposait un site e-commerce avec un système de téléchargement digital et de licences. Le site était construit avec React et Laravel.",
			tags: ['Laravel', 'React', 'SEO'],
			domain: 'Développement Web',
			buttons: [
				{ name: 'Voir sur GitHub', link: 'https://github.com/Romain-GUILLEMOT/bagou450', color: 'bg-blue-600' },
				{ name: 'Visiter le site', link: 'https://bagou450.com', color: 'bg-gray-600' }
			],
			source: true
		},
		{
			image: '/img/projects/hackaton2024.png',
			name: 'Hackaton 2024',
			description: "Projet réalisé lors du hackathon de SupDeVinci en collaboration avec Néosoft en 2024. J'ai appris à utiliser ArgoCD, Loki, Mimir, Tempo, ainsi qu'Otel.",
			tags: ['Kubernetes', 'ArgoCD', 'DevOps', 'Néosoft'],
			domain: 'DevOps',
			done: true,
			buttons: [
				{
					name: 'Voir sur GitHub',
					link: 'https://github.com/Romain-GUILLEMOT/Hackaton-2024-SDV/tree/main',
					color: 'bg-blue-600'
				},
				{
					name: 'Rapport Final',
					link: 'https://s.craft.me/xBkQ6VTcAtxrhP',
					color: 'bg-yellow-600'
				}
			],
			source: true
		},
		{
			image: '/img/projects/unraid.png',
			name: 'HomeLab',
			done: true,
			description: "Un lab maison pour expérimenter avec la gestion des containers et des machines virtuelles, mis en place avec Unraid. Ce projet m'a permis de travailler sur l'optimisation des ressources et la gestion des services auto-hébergés.",
			tags: ['Unraid', 'Containers', 'Virtualisation'],
			domain: 'Infrastructure',
			buttons: []
		},
		{
			image: '/img/projects/zelkoa.png',
			name: 'Zelkoa',
			done: true,
			description: "Zelkoa est un serveur Minecraft dédié à la survie et au jeu moddé. Ce projet m'a permis de découvrir la gestion d'un serveur de jeu et la configuration avancée de mods.",
			tags: ['Minecraft', 'Java'],
			domain: 'Gaming',
			buttons: []
		},
		{
			image: '/img/projects/cloudflare.png',
			name: 'Cloudflare DNS Web',
			done: true,
			description: "Client web pour la gestion des DNS Cloudflare, développé dans le cadre d'un projet à SupDeVinci. L'application permet une gestion simplifiée des enregistrements DNS via une interface web.",
			tags: ['Cloudflare', 'DNS', 'Développement Web'],
			domain: 'Développement web',
			buttons: [
				{
					name: 'Voir sur GitHub',
					link: 'https://github.com/Romain-GUILLEMOT/CloudflareDNSManager',
					color: 'bg-blue-600'
				}
			],
			source: true
		},
		{
			image: '/img/projects/locauto.png',
			name: 'Locauto',
			done: true,
			description: "Site de location de voitures développé dans le cadre d'un projet à SupDeVinci. Ce projet inclut la gestion des réservations et des véhicules disponibles, avec une interface utilisateur fluide.",
			tags: ['Laravel', 'React', 'Gestion de Projets'],
			domain: 'Développement Web',
			buttons: [
				{
					name: 'Voir sur GitHub',
					link: 'https://github.com/Romain-GUILLEMOT/LocautoLaravel',
					color: 'bg-blue-600'
				}
			],
			source: true
		}
	];

	export let tagColors: { [key: string]: TagColor } = {
		"react": { bg: "bg-blue-500", text: "text-white" },
		"laravel": { bg: "bg-red-500", text: "text-white" },
		"home assistant": { bg: "bg-yellow-500", text: "text-black" },
		"docker": { bg: "bg-blue-700", text: "text-white" },
		"debian": { bg: "bg-red-600", text: "text-white" },
		"ubuntu": { bg: "bg-[#E95420]", text: "text-white" },
		"unraid": { bg: "bg-green-600", text: "text-white" },
		"proxmox": { bg: "bg-purple-500", text: "text-white" },
		"kubernetes": { bg: "bg-blue-600", text: "text-white" },
		"vmware workstation": { bg: "bg-gray-600", text: "text-white" },
		"svelte": { bg: "bg-orange-400", text: "text-black" },
		"rust": { bg: "bg-red-700", text: "text-white" },
		"cargo": { bg: "bg-yellow-600", text: "text-black" },
		"go": { bg: "bg-blue-400", text: "text-white" },
		"php": { bg: "bg-indigo-500", text: "text-white" },
		"javascript": { bg: "bg-[#F7DF1E]", text: "text-black" },
		"nodejs": { bg: "bg-green-500", text: "text-white" },
		"seo": { bg: "bg-yellow-500", text: "text-black" },
		"gestion de projet": { bg: "bg-blue-600", text: "text-white" },
		"devops": { bg: "bg-gray-700", text: "text-white" },
		"neosoft": { bg: "bg-blue-300", text: "text-white" },
		"argocd": { bg: "bg-teal-600", text: "text-white" },
		"commerce electronique": { bg: "bg-purple-400", text: "text-white" },
		"containers": { bg: "bg-teal-500", text: "text-white" },
		"virtualisation": { bg: "bg-indigo-700", text: "text-white" },
		"minecraft": { bg: "bg-green-500", text: "text-white" },
		"cloudflare": { bg: "bg-blue-600", text: "text-white" },
		"dns": { bg: "bg-gray-500", text: "text-white" },
		"discord": { bg: "bg-purple-600", text: "text-white" },
		"automatisation": { bg: "bg-yellow-600", text: "text-black" }
	};

</script>

<svelte:head>
	<title>Romain GUILLEMOT - Mes projets</title>
	<meta name="description" content="Projets de  Romain GUILLEMOT" />
</svelte:head>

<main>
	<div class="mx-auto max-w-3xl px-4 sm:px-6 lg:max-w-7xl lg:px-8">
		<div class="py-24 text-center">
			<h1 class="text-4xl font-bold tracking-tight text-gray-900">Mes Projets</h1>
			<p class="mx-auto mt-4 max-w-3xl text-base text-gray-500">Explorez les projets que j'ai réalisés, ainsi que les
				technologies et outils utilisés pour leur conception.</p>
		</div>
	</div>
</main>

<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8 p-8">
	{#each projects as project}
		<div class="flex flex-col overflow-hidden rounded-lg shadow-lg">
			<div class="flex-shrink-0 border-4 border-gray-200">
				<button class="h-48 w-full object-cover object-top cursor-pointer off " on:click={() => showModal(project.image)}>
					<img src={project.image} alt={project.name} />
				</button>

			</div>
			{#if modalVisible}
				<div class="fixed inset-0 flex items-center justify-center bg-black bg-opacity-75 z-40">
					<button
						tabindex="0"
						class="bg-blue-500 rounded-lg px-2 py-2 absolute top-0 right-0 m-4 text-white text-3xl cursor-pointer flex items-center justify-center"
						on:click={closeModal}>
						&times;
					</button>

					<img src={modalImageSrc} alt="Grande {project.name}" class="max-h-full max-w-full" />
				</div>
			{/if}
			<div class="flex-1 flex flex-col justify-between bg-white p-6">
				<div class="flex-1">
					<h2 class="text-xl font-semibold text-gray-900 flex items-center gap-2">
						{project.name}
						<span
							class={project.done ? 'rounded-full bg-green-100 text-green-800 px-3 py-1 text-xs font-semibold' : 'rounded-full bg-yellow-100 text-yellow-800 px-3 py-1 text-xs font-semibold'}>
						  {project.done ? 'Terminé' : 'En cours'}
						</span>
					</h2>
					<div class="flex flex-wrap gap-2 mt-2">
						{#each project.tags as tag}
							<span
								class={`tag ${tagColors[normalizeTag(tag)]?.bg || 'bg-gray-400'} ${tagColors[normalizeTag(tag)]?.text || 'text-white'} rounded-md px-2 py-1`}>{tag}</span>
						{/each}
					</div>
					<p class="mt-3 text-base text-gray-500">{project.description}</p>
				</div>
				<div class="mt-6 text-sm text-gray-600 italic flex">
					<p>{project.domain}</p>
					{#if !project.source}
						<span class="private-source text-gray-500 opacity-75 text-sm ml-auto">Source privée</span>
					{/if}
				</div>
				{#if project.buttons}
					<div class="mt-4 flex flex-wrap gap-4">
						{#each project.buttons as button}
							<a href={button.link} target="_blank"
								 class={`rounded-md ${button.color} px-3.5 py-2.5 text-sm font-semibold text-white shadow-sm hover:${button.color.replace('bg-', 'hover:bg-')} focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-${button.color.split('-')[1]}`}>{button.name}</a>
						{/each}
					</div>
				{/if}

			</div>
		</div>
	{/each}
</div>

<svelte:window on:keydown|preventDefault={onKeyDown} />