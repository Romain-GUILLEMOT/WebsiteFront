<script lang="ts">
	function normalizeTag(tag: string) {
		return tag.normalize("NFD").replace(/[\u0300-\u036f]/g, "").toLowerCase();
	}

	type TagColor = {
		bg: string;
		text: string;
	};

	export let tagColors: { [key: string]: TagColor } = {
		"android": { bg: "bg-green-500", text: "text-white" },
		"bachelor": { bg: "bg-blue-600", text: "text-white" },
		"bootloader": { bg: "bg-gray-600", text: "text-white" },
		"cdd": { bg: "bg-pink-500", text: "text-white" },
		"css": { bg: "bg-blue-400", text: "text-white" },
		"capricehost": { bg: "bg-red-700", text: "text-white" },
		"communication": { bg: "bg-teal-500", text: "text-white" },
		"discord": { bg: "bg-blue-600", text: "text-white" },
		"docker": { bg: "bg-blue-700", text: "text-white" },
		"developpement web": { bg: "bg-orange-400", text: "text-black" },
		"entreprise": { bg: "bg-green-600", text: "text-white" },
		"go": { bg: "bg-blue-400", text: "text-white" },
		"gestion de projet": { bg: "bg-blue-600", text: "text-white" },
		"html": { bg: "bg-blue-300", text: "text-white" },
		"java": { bg: "bg-red-500", text: "text-white" },
		"laravel": { bg: "bg-red-500", text: "text-white" },
		"linux": { bg: "bg-orange-500", text: "text-white" },
		"minecraft": { bg: "bg-green-400", text: "text-white" },
		"nodejs": { bg: "bg-green-500", text: "text-white" },
		"ozlaloc": { bg: "bg-blue-600", text: "text-white" },
		"php": { bg: "bg-indigo-500", text: "text-white" },
		"panel de jeux": { bg: "bg-yellow-500", text: "text-black" },
		"portfolio": { bg: "bg-yellow-500", text: "text-black" },
		"protocole ip": { bg: "bg-gray-600", text: "text-white" },
		"proxmox": { bg: "bg-purple-500", text: "text-white" },
		"pterodactyl": { bg: "bg-purple-600", text: "text-white" },
		"react": { bg: "bg-blue-500", text: "text-white" },
		"root": { bg: "bg-red-500", text: "text-white" },
		"reseau": { bg: "bg-teal-500", text: "text-white" },
		"reseaux": { bg: "bg-teal-500", text: "text-white" },
		"support client": { bg: "bg-green-700", text: "text-white" },
		"securite": { bg: "bg-red-600", text: "text-white" },
		"vmware workstation": { bg: "bg-gray-600", text: "text-white" },
		"vpn": { bg: "bg-yellow-400", text: "text-black" },
		"vps": { bg: "bg-red-300", text: "text-white" },
		"virtualisation": { bg: "bg-blue-300", text: "text-white" },
		"virtualizor": { bg: "bg-purple-500", text: "text-white" },
		"wordpress": { bg: "bg-blue-500", text: "text-white" },
		"etudes": { bg: "bg-indigo-400", text: "text-white" },
		"hackathon": { bg: "bg-orange-500", text: "text-white" },
		"ia": { bg: "bg-purple-600", text: "text-white" },
		"kubernetes": { bg: "bg-blue-700", text: "text-white" },
		"banque": { bg: "bg-green-500", text: "text-white" },
		"domotique": { bg: "bg-teal-400", text: "text-white" },
		"education": { bg: "bg-yellow-200", text: "text-black" },
		"politique": { bg: "bg-red-500", text: "text-white" },
		"esp": { bg: "bg-gray-400", text: "text-white" },
		"home assistant": { bg: "bg-yellow-400", text: "text-black" },
		"mqtt": { bg: "bg-purple-300", text: "text-white" },
		"react native": { bg: "bg-blue-300", text: "text-white" },
		"portainer": { bg: "bg-teal-600", text: "text-white" },
		"electronique": { bg: "bg-orange-600", text: "text-white" },
		"rennes": { bg: "bg-purple-400", text: "text-white" },
		"rpi": { bg: "bg-green-400", text: "text-white" },
		"evenement": { bg: "bg-red-400", text: "text-white" }
	};
	export let parcours = [
		{
			annee: "2015",
			age: "9 ans - 10 ans",
			details: [
				{
					titre: "Minecraft",
					description: "J'ai voulu ouvrir un serveur Minecraft, je me suis donc lancé dans le développement de plugins Minecraft en Java.",
					image: "/img/past/minecraft.webp",
					couleur: "#34D399",
					tags: ["Minecraft", "Java"]
				},
				{
					titre: "HTML/CSS",
					description: "Pour le serveur Minecraft, j'avais aussi créé un site statique (HTML/CSS) et appris les bases de ces langages de description.",
					image: "/img/past/html.webp",
					couleur: "#FF5733",
					tags: ["HTML", "CSS"]
				},
				{
					titre: "Virtualisation et VPS",
					description: "Création de mes premières VMs avec VirtualBox et apprentissage de Linux. Location de mon premier VPS chez Dedibox, apprentissage de Linux.",
					image: "/img/past/linux.webp",
					couleur: "#1E90FF",
					tags: ["Virtualisation", "Linux", "VPS"]
				}
			]
		},
		{
			annee: "2016",
			age: "10 ans - 11 ans",
			details: [
				{
					titre: "Mods Minecraft",
					description: "Création de mon premier mod Minecraft en Java.",
					image: "/img/past/minecraft-mods.webp",
					couleur: "#a634d3",
					tags: ["Java", "Minecraft"]
				},
				{
					titre: "Rootage de téléphone",
					description: "Premier rootage de téléphone, apprentissage des notions de bootloader, etc.",
					image: "/img/past/phone-root.webp",
					couleur: "#FF5733",
					tags: ["Root", "Android", "Bootloader"]
				}
			]
		},
		{
			annee: "2017",
			age: "11 ans - 12 ans",
			details: [
				{
					titre: "Réseaux et VPN",
					description: "Bases réseaux, apprentissage du protocole IP pour la configuration de VPN et de tunnels GRE.",
					image: "/img/past/network.webp",
					couleur: "#1E90FF",
					tags: ["Réseaux", "VPN", "Protocole IP"]
				}
			]
		},
		{
			annee: "2018",
			age: "12 ans - 13 ans",
			details: [
				{
					titre: "Pterodactyl",
					description: "Première prise en main du panel de jeux Pterodactyl utilisant Docker.",
					image: "/img/past/pterodactyl.webp",
					couleur: "#FFA500",
					tags: ["Docker", "Pterodactyl", "Panel de jeux"]
				},
				{
					titre: "VMware Workstation",
					description: "Prise en main de VMware Workstation Pro pour une meilleure gestion des VMs.",
					image: "/img/past/vmware.webp",
					couleur: "#FF5733",
					tags: ["VMware Workstation", "Virtualisation"]
				}
			]
		},
		{
			annee: "2019",
			age: "13 ans - 14 ans",
			details: [
				{
					titre: "PureCPU",
					description: "Aide aux clients de PureCPU (entreprise fermée) à configurer leurs réseaux et installer des panels de jeux ou autres services sur Linux (Linux avancé et réseaux débutant).",
					image: "/img/past/purecpu.webp",
					couleur: "#781eff",
					tags: ["Linux", "Réseaux", "Support client"]
				},
				{
					titre: "Proxmox",
					description: "Prise en main de Proxmox pour la gestion des machines virtuelles de PureCPU.",
					image: "/img/past/proxmox.webp",
					couleur: "#FFA500",
					tags: ["Proxmox", "Virtualisation"]
				}
			]
		},
		{
			annee: "2020",
			age: "14 ans - 15 ans",
			details: [
				{
					titre: "CapriceHost",
					description: "Responsable de l'infrastructure réseau, système et web de CapriceHost. Premières prises en main de PHP (Laravel), React et Golang.",
					image: "/img/past/capricehost.webp",
					couleur: "#ff2097",
					tags: ["Laravel", "React", "GO", "PHP"]
				},
				{
					titre: "Bot Discord NodeJS",
					description: "Création d'un bot Discord avec NodeJS pour CapriceHost.",
					image: "/img/past/discord-bot.webp",
					couleur: "#34D399",
					tags: ["NodeJS", "Discord"]
				},
				{
					titre: "Pterodactyl",
					description: "Création du premier module additionnel pour le panel de jeux Pterodactyl.",
					image: "/img/past/pterodactyl-mod.webp",
					couleur: "#FFA500",
					tags: ["Panel de jeux", "Laravel", "React", "PHP"]
				},
				{
					titre: "Virtualizor",
					description: "Prise en main de Virtualizor pour la gestion des machines de CapriceHost.",
					image: "/img/past/virtualizor.webp",
					couleur: "#FF5733",
					tags: ["Virtualizor", "Virtualisation"]
				},
				{
					titre: "TutoEnFolie",
					description: "Création de TutoEnFolie visant à aider les professeurs de mon lycée à partager leur cours avec le monde (Disparue avec l'incendie de OVH Strasbourg).",
					image: "/img/past/tutoenfolie.webp",
					couleur: "#FFA500",
					tags: ["Éducation", "Lycée", "Partage"]
				},

			]
		},
		{
			annee: "2021",
			age: "15 ans - 16 ans",
			details: [
				{
					titre: "Modules Pterodactyl",
					description: "Première vente de modules additionnels pour Pterodactyl, nécessitant d'améliorer la qualité de mon code en Laravel, React et Go face à la concurrence.",
					image: "/img/past/pterodactyl-sale.webp",
					couleur: "#FF2D20",
					tags: ["Pterodactyl", "Laravel", "React", "GO"]
				},
				{
					titre: "Visio conférence avec Gabriel Attal",
					description: "Visio conférence avec Gabriel Attal au sujet du lycée Simone Veil.",
					image: "/img/past/gabriel-attal.webp",
					couleur: "#FF5733",
					tags: ["Politique", "Éducation"]
				}
			]
		},
		{
			annee: "2022",
			age: "16 ans - 17 ans",
			details: [
				{
					titre: "Développement quotidien",
					description: "Développement en React, Laravel et Go quotidiennement, grande amélioration des connaissances dans ces langages.",
					image: "/img/past/dev-everyday.webp",
					couleur: "#34D399",
					tags: ["React", "Laravel", "GO"]
				},
				{
					titre: "CapriceHost",
					description: "Renforcement des systèmes réseau et de protection pour CapriceHost en réponse aux partenariats avec des YouTubers.",
					image: "/img/past/youtuber-partnership.webp",
					couleur: "#FF5733",
					tags: ["Réseau", "Sécurité", "CapriceHost"]
				},
				{
					titre: "Festival La Dinguerie 2",
					description: "Organisation du festival La Dinguerie 2 à Rennes, création d'une borne d'acadé pour cet événement avec un RPI.",
					image: "/img/past/dinguerie.webp",
					couleur: "#FFA500",
					tags: ["Événement", "Rennes", "RPI"]
				},
				{
					titre: "Client Web pour la banque Kard",
					description: "Création d'un client web privé pour la banque Kard.",
					image: "/img/past/kard.webp",
					couleur: "#34D399",
					tags: ["Banque", "Web"]
				},
				{
					titre: "Ruche Connectée",
					description: "Création d'une ruche connectée avec le lycée Simone Veil (Conception 3D à l'électronique au code) qui est maintenant sur la mairie de Liffré.",
					image: "/img/past/ruche.webp",
					couleur: "#FF5733",
					tags: ["Éducation", "Électronique"]
				},
				{
					titre: "Invitation à l'Assemblée nationale",
					description: "Invitation à l'Assemblée nationale par un député suite à La Dinguerie 2.",
					image: "/img/past/assemblee.webp",
					couleur: "#FF2D20",
					tags: ["Politique", "Événement"]
				},
			]
		},
		{
			annee: "2023",
			age: "17 ans - 18 ans",
			details: [
				{
					titre: "Bagou450",
					description: "Ouverture de mon entreprise Bagou450 pour la vente de modules liés à Pterodactyl.",
					image: "/img/past/bagou450.webp",
					couleur: "#FFA500",
					tags: ["Entreprise", "Pterodactyl"]
				},
				{
					titre: "Site Bagou450",
					description: "Création du site de Bagou450 avec système de licence de vente en ligne (React + Laravel).",
					image: "/img/past/bagou450-site.webp",
					couleur: "#34D399",
					tags: ["React", "Laravel"]
				},
				{
					titre: "Bot Discord Golang",
					description: "Création d'un bot Discord en Golang pour Bagou450.",
					image: "/img/past/discord-bot-go.webp",
					couleur: "#FF2D20",
					tags: ["GO"]
				},
				{
					titre: "Ozlaloc",
					description: "Contrat avec Ozlaloc pour améliorer leurs différents WordPress et créer un site en React avec un backend Laravel.",
					image: "/img/past/ozlaloc-site.webp",
					couleur: "#1E90FF",
					tags: ["WordPress", "React", "Laravel"]
				},
				{
					titre: "SupDeVinci",
					description: "Entrée à SupDeVinci en tant que première année de bachelor à Chantepie.",
					image: "/img/past/supdevinci.webp",
					couleur: "#FF5733",
					tags: ["Études", "Bachelor"]
				},

				{
					titre: "Agrégation de connexion Internet",
					description: "Agrégation de connexion Internet via OpenMPTCPRouter, ce qui m'a appris beaucoup de choses en réseaux comme la gestion de sous-réseaux, etc.",
					image: "/img/past/openmptcprouter.webp",
					couleur: "#34D399",
					tags: ["Réseaux"]
				},
				{
					titre: "Gestion de conteneurs Docker",
					description: "Gestion de conteneurs Docker via Portainer pour Bagou450.",
					image: "/img/past/portainer.webp",
					couleur: "#1E90FF",
					tags: ["Docker", "Portainer"]
				}
			]
		},
		{
			annee: "2024",
			age: "18 ans - 19 ans",
			details: [
				{
					titre: "SupDeVinci",
					description: "Apprentissage de la communication web, expression orale et connaissances de l'entreprise.",
					image: "/img/past/supdevinci.webp",
					couleur: "#1E90FF",
					tags: ["Communication", "Études", "Entreprise"]
				},
				{
					titre: "Travail avec NeoSoft",
					description: "Travail avec NeoSoft dans le contexte du Hackathon 2024 (événement de SupDeVinci) avec début avec K8S, ArgoCD, etc., avec un tag DevOps important.",
					image: "/img/past/neosoft.webp",
					couleur: "#1E90FF",
					tags: ["DevOps", "Kubernetes", "Hackathon"]
				},
				{
					titre: "Application Android BagouWaller",
					description: "Création d'une application Android en React Native BagouWaller pour faire une agrégation de différentes banques.",
					image: "/img/past/bagouwaller.webp",
					couleur: "#34D399",
					tags: ["React Native", "Banque"]
				},
				{
					titre: "Switch HDMI connecté",
					description: "Création d'un switch HDMI connecté avec un ESP et du MQTT.",
					image: "/img/past/switch-hdmi.webp",
					couleur: "#FFA500",
					tags: ["ESP", "MQTT"]
				},
				{
					titre: "Assistant vocal AI",
					description: "Création d'un assistant vocal AI pour Home Assistant.",
					image: "/img/past/assistant-vocal.webp",
					couleur: "#FF5733",
					tags: ["IA", "Domotique", "Home Assistant"]
				},
				{
					titre: "Ozlaloc",
					description: "Fermeture de Bagou450 et CDD avec Ozlaloc pour se concentrer sur la création de leur site internet jusqu'en 2025.",
					image: "/img/past/ozlaloc-cdd.webp",
					couleur: "#FFA500",
					tags: ["CDD", "Ozlaloc", "Développement web"]
				},
				{
					titre: "SupDeVinci - Deuxième année",
					description: "Deuxième année de bachelor à SupDeVinci, apprentissage de la gestion de projet de groupe.",
					image: "/img/past/supdevinci-2nd-year.webp",
					couleur: "#34D399",
					tags: ["Gestion de projet", "Études"]
				},
				{
					titre: "RomainGuillemot.dev",
					description: "Création du site romainguillemot.dev pour servir de portfolio et CV en ligne.",
					image: "/img/past/romain-site.webp",
					couleur: "#FF2D20",
					tags: ["Portfolio", "CV"]
				},

			]
		}
	];


</script>

<main>
	<div class="mx-auto max-w-3xl px-4 sm:px-6 lg:max-w-7xl lg:px-8">
		<div class="py-24 text-center">
			<h1 class="text-4xl font-bold tracking-tight text-gray-900">Mon parcours</h1>
			<p class="mx-auto mt-4 max-w-3xl text-base text-gray-500">Parcours d'apprentissage et d'expériences professionnelles</p>
		</div>
	</div>
</main>

<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8 p-8 text-center">
	{#each parcours as anneeData}
		<div class="border rounded-lg p-4 shadow-lg">
				<h2 class="text-2xl font-semibold mb-4 " style="color: {anneeData.details[0].couleur};">{anneeData.annee}</h2>
			<span class="rounded-full bg-green-100 text-green-800 px-3 py-1 text-xs font-semibold">{anneeData.age}</span>

			{#each anneeData.details as detail}
				<div class="mb-4 mt-4">
					<img src="{detail.image}" alt="{detail.titre}" class="h-16 w-16 mx-auto mb-2" />
					<h3 class="text-xl font-bold">{detail.titre}</h3>
					<div class="my-2 ">
						{#each detail.tags as tag}
							<span class={`tag ${tagColors[normalizeTag(tag)]?.bg || 'bg-gray-400'} ${tagColors[normalizeTag(tag)]?.text || 'text-white'} rounded-md px-2 py-1 mx-2`}>{tag}</span>
						{/each}
					</div>
					<p class="text-gray-600">{detail.description}</p>

				</div>
			{/each}
		</div>
	{/each}
</div>

<svelte:window on:keydown|preventDefault={onKeyDown} />