<script>
	import { fade } from 'svelte/transition';

</script>

<svelte:head>
	<title>Alternance - Romain GUILLEMOT</title>
	<meta name="description" content="Alternance de Romain GUILLEMOT, étudiant en deuxième année de Bachelor à SupDeVinci Rennes" />
</svelte:head>

<div class="bg-white py-24 sm:py-32">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div
			class="mx-auto grid max-w-2xl grid-cols-1 items-start gap-x-8 gap-y-16 sm:gap-y-24 lg:mx-0 lg:max-w-none lg:grid-cols-2">
			<!-- Image et Citation -->
			<div class="lg:pr-4">
				<div
					class="relative overflow-hidden rounded-3xl bg-gray-900 px-6 pb-9 pt-64 shadow-2xl sm:px-12 lg:max-w-lg lg:px-8 lg:pb-8 xl:px-10 xl:pb-10 transition-transform duration-500 transform hover:scale-105">
					<img class="absolute inset-0 h-full w-full object-cover brightness-90 saturate-50"
							 src="/img/bg.jpg!w700wp"
							 alt="Infrastructure DevOps" loading="lazy">
					<div class="absolute inset-0 bg-gray-900 mix-blend-multiply"></div>
					<div class="absolute left-1/2 top-1/2 -ml-16 -translate-x-1/2 -translate-y-1/2 transform-gpu blur-3xl"
							 aria-hidden="true">
						<div class="aspect-[1097/845] w-[68.5625rem] bg-gradient-to-tr from-[#ff4694] to-[#776fff] opacity-40"
								 style="clip-path: polygon(74.1% 44.1%, 100% 61.6%, 97.5% 26.9%, 85.5% 0.1%, 80.7% 2%, 72.5% 32.5%, 60.2% 62.4%, 52.4% 68.1%, 47.5% 58.3%, 45.2% 34.5%, 27.5% 76.7%, 0.1% 64.9%, 17.9% 100%, 27.6% 76.8%, 76.1% 97.7%, 74.1% 44.1%)"></div>
					</div>
					<figure class="relative isolate" transition:fade={{ duration: 500 }}>
						<svg xmlns="http://www.w3.org/2000/svg"  class="h-12 w-auto text-white mx-auto" viewBox="0 0 24 24"><path fill="currentColor" d="m12.89 3l1.96.4L11.11 21l-1.96-.4zm6.7 9L16 8.41V5.58L22.42 12L16 18.41v-2.83zM1.58 12L8 5.58v2.83L4.41 12L8 15.58v2.83z"/></svg>
						<blockquote class="mt-6 text-xl font-semibold leading-8 text-white text-center">
							<p>“Je suis à la recherche d'une entreprise pour mettre à profit mes compétences
								techniques et contribuer activement à des projets stimulants.”</p>
						</blockquote>
						<figcaption class="mt-6 text-sm leading-6 text-gray-300 text-center"><strong
							class="font-semibold text-white">Romain GUILLEMOT,</strong> étudiant en Bachelor
						</figcaption>
					</figure>
				</div>
			</div>
			<!-- Texte et Informations -->
			<div>
				<div class="text-base leading-7 text-gray-700 lg:max-w-lg">
					<p class="text-base font-semibold leading-7 text-indigo-600">Alternance</p>
					<h1 class="mt-2 text-4xl font-extrabold tracking-tight text-gray-900 sm:text-5xl">
						À la recherche d'une alternance en développement (ou DevOps)
					</h1>
					<div class="max-w-xl">
						<p class="mt-6 text-lg">
							Actuellement étudiant en <strong class="font-bold">deuxième année de Bachelor</strong> à SupDeVinci Rennes, je suis passionné par le développement logiciel et l'administration des systèmes. <strong class="font-bold">Je recherche une alternance à partir de mai 2024</strong> pour mettre à profit mes compétences en développement, acquérir de l'expérience pratique, et continuer à me perfectionner.
						</p>
						<p class="mt-8 text-lg">
							Bien que mon objectif principal soit de m'épanouir dans le développement, j'ai également une bonne compréhension des réseaux et de l'infrastructure. À l'avenir, je souhaite m'orienter vers le <strong class="font-bold">DevOps</strong> pour allier mes compétences en développement à une gestion optimisée des systèmes, en facilitant la collaboration entre les équipes.
						</p>
						<p class="mt-8 text-lg">
							Si vous recherchez un développeur motivé et passionné, prêt à s'engager pleinement et à évoluer au sein de votre entreprise, je serais heureux de discuter de l'opportunité de rejoindre votre équipe. Ensemble, nous pourrons bâtir des solutions innovantes et durables.
						</p>
					</div>
				</div>
				<dl class="mt-10 grid grid-cols-1 gap-8 sm:grid-cols-2 lg:grid-cols-3 border-t border-gray-200 pt-10">
					<div class="flex items-center gap-x-4">
						<div class="flex-none w-12 h-12 rounded-full bg-indigo-600 flex items-center justify-center text-white">
							🎓
						</div>
						<div>
							<dt class="text-sm font-semibold leading-6 text-gray-600">Études</dt>
							<dd class="mt-1 text-lg font-bold text-gray-900">Deuxième année de Bachelor SupDeVinci</dd>
						</div>
					</div>
					<div class="flex items-center gap-x-4">
						<div class="flex-none w-12 h-12 rounded-full bg-green-600 flex items-center justify-center text-white">
							📅
						</div>
						<div>
							<dt class="text-sm font-semibold leading-6 text-gray-600">Disponibilité</dt>
							<dd class="mt-1 text-lg font-bold text-gray-900">Mai 2024</dd>
						</div>
					</div>
					<div class="flex items-center gap-x-4">
						<div class="flex-none w-12 h-12 rounded-full bg-blue-600 flex items-center justify-center text-white">
							📍
						</div>
						<div>
							<dt class="text-sm font-semibold leading-6 text-gray-600">Localisation</dt>
							<dd class="mt-1 text-lg font-bold text-gray-900">Dourdain, France</dd>
						</div>
					</div>
				</dl>
				<div class="mt-10 flex space-x-4">
					<a href="mailto:contact@romain-guillemot.dev"
						 class="inline-flex items-center px-6 py-3 border border-transparent text-base font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 transition ease-in-out duration-150">
						Contactez-moi
					</a>
					<a href="/CV.pdf"
						 class="inline-flex items-center px-6 py-3 border border-transparent text-base font-medium rounded-md text-indigo-600 bg-white hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 transition ease-in-out duration-150">
						Voir mon CV
						<svg class="ml-2 -mr-1 h-5 w-5" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
								 stroke="currentColor" aria-hidden="true">
							<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3" />
						</svg>
					</a>
				</div>
			</div>
		</div>
	</div>
</div>