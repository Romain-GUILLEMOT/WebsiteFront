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
		"unraid": { bg: "bg-gray-800", text: "text-white" },
		"nas": { bg: "bg-yellow-500", text: "text-black" },
		"dns": { bg: "bg-green-600", text: "text-white" },
		"dhcp": { bg: "bg-red-500", text: "text-white" },
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
					titre: "Développement de Plugins Minecraft",
					description: "Initiation au développement de plugins Minecraft en Java pour la gestion d'un serveur privé.",
					image: "/img/past/minecraft.webp",
					couleur: "#34D399",
					tags: ["Minecraft", "Java"]
				},
				{
					titre: "Création d'un Site Web Statique",
					description: "Développement d'un site web statique en HTML/CSS pour accompagner le serveur Minecraft, avec acquisition des bases des langages front-end.",
					image: "/img/past/html.webp",
					couleur: "#FF5733",
					tags: ["HTML", "CSS"]
				},
				{
					titre: "Initiation à la Virtualisation",
					description: "Création de machines virtuelles avec VirtualBox et gestion de mon premier VPS sous Linux.",
					image: "/img/past/virtualbox.png",
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
					titre: "Création de Mods Minecraft",
					description: "Développement de mon premier mod Minecraft en Java, consolidant mes compétences en programmation.",
					image: "/img/past/java.png",
					couleur: "#a634d3",
					tags: ["Java", "Minecraft"]
				},
				{
					titre: "Rootage de Téléphone",
					description: "Expérience pratique dans le rootage de téléphone et compréhension des concepts de bootloader.",
					image: "/img/past/lineage.png",
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
					description: "Apprentissage des concepts réseaux et mise en place de VPN avec protocoles IP et tunnels GRE.",
					image: "/img/past/wireguard.png",
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
					titre: "Panel de Jeux Pterodactyl",
					description: "Première utilisation du panel de jeux Pterodactyl reposant sur Docker.",
					image: "/img/past/pterodactyl.png",
					couleur: "#FFA500",
					tags: ["Docker", "Pterodactyl", "Panel de jeux"]
				},
				{
					titre: "VMware Workstation",
					description: "Maîtrise de VMware Workstation pour une gestion optimisée des machines virtuelles.",
					image: "/img/past/vmware.png",
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
					titre: "Support Technique chez PureCPU",
					description: "Assistance aux clients de PureCPU pour la configuration réseau et l'installation de services sous Linux.",
					image: "/img/past/purecpu.png",
					couleur: "#781eff",
					tags: ["Linux", "Réseaux", "Support client"]
				},
				{
					titre: "Gestion de Machines Virtuelles avec Proxmox",
					description: "Prise en main de Proxmox pour la gestion des infrastructures virtualisées de PureCPU.",
					image: "/img/past/proxmox.png",
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
					titre: "Responsable Technique chez CapriceHost",
					description: "Gestion complète des infrastructures réseau, système et web, avec initiation à PHP (Laravel), React et Go.",
					image: "/img/past/capricehost.png",
					couleur: "#ff2097",
					tags: ["Laravel", "React", "Go", "PHP"]
				},
				{
					titre: "Bot Discord en NodeJS",
					description: "Développement d'un bot Discord en NodeJS pour CapriceHost.",
					image: "/img/past/discordjs.png",
					couleur: "#34D399",
					tags: ["NodeJS", "Discord"]
				},
				{
					titre: "Module Additionnel pour Pterodactyl",
					description: "Création d'un module personnalisé pour le panel de jeux Pterodactyl.",
					image: "/img/past/pterodactyl.png",
					couleur: "#FFA500",
					tags: ["Panel de jeux", "Laravel", "React", "PHP"]
				},
				{
					titre: "Gestion de Machines avec Virtualizor",
					description: "Utilisation de Virtualizor pour la gestion des serveurs de CapriceHost.",
					image: "/img/past/virtualizor.png",
					couleur: "#FF5733",
					tags: ["Virtualizor", "Virtualisation"]
				},
				{
					titre: "Création de TutoEnFolie",
					description: "Conception de TutoEnFolie, une plateforme éducative pour le partage des cours, malheureusement perdue après l'incendie d'OVH.",
					image: "/img/past/ovhfire.png",
					couleur: "#FFA500",
					tags: ["Éducation", "Lycée", "Partage"]
				}
			]
		},
		{
			annee: "2021",
			age: "15 ans - 16 ans",
			details: [
				{
					titre: "Vente de Modules Pterodactyl",
					description: "Première commercialisation de modules pour Pterodactyl, impliquant l'amélioration continue en Laravel, React et Go.",
					image: "/img/past/pterodactyl.png",
					couleur: "#FF2D20",
					tags: ["Pterodactyl", "Laravel", "React", "Go"]
				},
				{
					titre: "Visio-conférence avec Gabriel Attal",
					description: "Participation à une visio-conférence avec Gabriel Attal sur l'avenir du lycée Simone Veil.",
					image: "/img/past/teams.png",
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
					titre: "Développement Intensif",
					description: "Perfectionnement quotidien en développement avec React, Laravel et Go.",
					image: "/img/past/golang.png",
					couleur: "#34D399",
					tags: ["React", "Laravel", "Go"]
				},
				{
					titre: "Sécurisation chez CapriceHost",
					description: "Renforcement des systèmes de sécurité en réponse aux partenariats stratégiques de CapriceHost.",
					image: "/img/past/capricehost.png",
					couleur: "#FF5733",
					tags: ["Réseau", "Sécurité", "CapriceHost"]
				},
				{
					titre: "Organisation d'Événements - La Dinguerie 2",
					description: "Organisation du festival La Dinguerie 2 à Rennes, avec développement d'une bande arcade via Raspberry Pi.",
					image: "/img/past/ding.png",
					couleur: "#FFA500",
					tags: ["Événement", "Rennes", "RPI"]
				},
				{
					titre: "Développement pour la Banque Kard",
					description: "Conception d'un client web privé pour la gestion bancaire de Kard.",
					image: "/img/past/kard.png",
					couleur: "#34D399",
					tags: ["Banque", "Web"]
				},
				{
					titre: "Projet Ruche Connectée",
					description: "Développement d'une ruche connectée au lycée Simone Veil, maintenant installée à la mairie de Liffré.",
					image: "/img/past/solidworks.png",
					couleur: "#FF5733",
					tags: ["Éducation", "Électronique"]
				},
				{
					titre: "Invitation à l'Assemblée Nationale",
					description: "Invitation officielle à l'Assemblée Nationale par un député suite au succès de La Dinguerie 2.",
					image: "/img/past/anationale.png",
					couleur: "#FF2D20",
					tags: ["Politique", "Événement"]
				}
			]
		},
		{
			annee: "2023",
			age: "17 ans - 18 ans",
			details: [
				{
					titre: "Lancement de Bagou450",
					description: "Création de l'entreprise Bagou450, spécialisée dans la vente de modules pour Pterodactyl.",
					image: "/img/past/bagou450.png",
					couleur: "#FFA500",
					tags: ["Entreprise", "Pterodactyl"]
				},
				{
					titre: "Développement du Site Web de Bagou450",
					description: "Conception du site de Bagou450 avec un système de licences et de vente en ligne.",
					image: "/img/past/bagou450.png",
					couleur: "#34D399",
					tags: ["React", "Laravel"]
				},
				{
					titre: "Bot Discord en Go",
					description: "Développement d'un bot Discord en Go pour automatiser les services de Bagou450.",
					image: "/img/past/golang.png",
					couleur: "#FF2D20",
					tags: ["Go"]
				},
				{
					titre: "Collaboration avec Ozlaloc",
					description: "Développement du site web d'Ozlaloc en React et Laravel, ainsi que la gestion de leurs plateformes WordPress.",
					image: "/img/past/ozlaloc.png",
					couleur: "#1E90FF",
					tags: ["WordPress", "React", "Laravel"]
				},
				{
					titre: "Entrée à SupDeVinci",
					description: "Inscription en première année de Bachelor à SupDeVinci Chantepie, avec un focus sur les technologies du web.",
					image: "/img/past/supdevinci.png",
					couleur: "#FF5733",
					tags: ["Études", "Bachelor"]
				},
				{
					titre: "Agrégation de Connexion Internet",
					description: "Mise en place d'une agrégation de connexion Internet avec OpenMPTCPRouter pour une gestion avancée des réseaux.",
					image: "/img/past/omr-logo.png",
					couleur: "#34D399",
					tags: ["Réseaux"]
				},
				{
					titre: "Gestion des Conteneurs Docker",
					description: "Administration de conteneurs Docker via Portainer pour les services de Bagou450.",
					image: "/img/past/docker.png",
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
					titre: "Seconde Année à SupDeVinci",
					description: "Approfondissement de la communication web, expression orale et des connaissances d'entreprise en deuxième année de bachelor.",
					image: "/img/past/supdevinci.png",
					couleur: "#1E90FF",
					tags: ["Communication", "Études", "Entreprise"]
				},
				{
					titre: "Collaboration avec NeoSoft",
					description: "Participation au Hackathon 2024 de SupDeVinci en partenariat avec NeoSoft, première expérience avec K8S et ArgoCD.",
					image: "/img/past/neosoft.png",
					couleur: "#1E90FF",
					tags: ["DevOps", "Kubernetes", "Hackathon"]
				},
				{
					titre: "Application Android BagouWallet",
					description: "Développement d'une application Android en React Native pour l'agrégation de comptes bancaires.",
					image: "/img/past/reactnative.png",
					couleur: "#34D399",
					tags: ["React Native", "Banque"]
				},
				{
					titre: "Switch HDMI Connecté",
					description: "Création d'un switch HDMI connecté utilisant un ESP et MQTT pour la gestion à distance.",
					image: "/img/past/mqtt.png",
					couleur: "#FFA500",
					tags: ["ESP", "MQTT"]
				},
				{
					titre: "Assistant Vocal IA",
					description: "Développement d'un assistant vocal basé sur l'IA pour l'intégration dans Home Assistant.",
					image: "/img/past/ha.png",
					couleur: "#FF5733",
					tags: ["IA", "Domotique", "Home Assistant"]
				},
				{
					titre: "CDD chez Ozlaloc",
					description: "Focus sur le développement du site web d'Ozlaloc après la fermeture de Bagou450, en CDD jusqu'en 2025.",
					image: "/img/past/ozlaloc.png",
					couleur: "#FFA500",
					tags: ["CDD", "Ozlaloc", "Développement web"]
				},
				{
					titre: "Homelab",
					description: "Implémentation d'un Homelab basé sur Unraid, incluant la gestion de NAS, conteneurs Docker, DNS, DHCP, et autres services essentiels.",
					image: "/img/past/unraid.png",
					couleur: "#1E90FF",
					tags: ["Unraid", "NAS", "Docker", "DNS", "DHCP"]
				},
				{
					titre: "Deuxième Année à SupDeVinci",
					description: "Études approfondies en gestion de projet de groupe dans le cadre de ma deuxième année de bachelor.",
					image: "/img/past/supdevinci.png",
					couleur: "#34D399",
					tags: ["Gestion de projet", "Études"]
				},
				{
					titre: "Portfolio en Ligne",
					description: "Création du site romain-guillemot.dev comme portfolio et CV professionnel en ligne.",
					image: "/img/logo.png",
					couleur: "#FF2D20",
					tags: ["Portfolio", "CV"]
				}
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
					<img src="{detail.image}" alt="{detail.titre}" class="max-h-24 min-h-16 min-w-16 max-w-24 mx-auto mb-2" />
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