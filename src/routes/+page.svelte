<script>
	import Skills from '../components/Main/Skills.svelte';
	import { onMount } from 'svelte';
	import { fly } from 'svelte/transition';
	import Projects from '../components/Main/Projects.svelte';
	import Github from '../components/Main/Github.svelte';

	let isVisible = true;
	let isOpen = false;

	const editDialog = () => {
		isOpen = !isOpen;
	};
	onMount(() => {
		const handleScroll = () => {
			isVisible = window.scrollY < 50;
		};

		window.addEventListener('scroll', handleScroll);

		return () => {
			window.removeEventListener('scroll', handleScroll);
		};
	});
	function scrollToSkills() {
		const skillsSection = document.getElementById('skills');
		if (skillsSection) {
			skillsSection.scrollIntoView({ behavior: 'smooth' });
		}
	}
</script>

<svelte:head>
	<title>Romain GUILLEMOT - Accueil</title>
	<meta name="description" content="Projets, Parcours et Informations sur Romain GUILLEMOT" />
</svelte:head>
<div>
</div>
<div class="bg-white">
	<header class="absolute inset-x-0 top-0 z-50">
		<nav class="mx-auto flex max-w-7xl items-center justify-between p-6 lg:px-8" aria-label="Global">
			<div class="flex lg:flex-1">
				<a href="/" class="-m-1.5 p-1.5">
					<span class="sr-only">Romain Guillemot</span>
					<img class="h-16 w-auto" src="/img/logo.png" alt="">
				</a>
			</div>
			<div class="flex lg:hidden">
				<button type="button" on:click={editDialog} class="-m-2.5 inline-flex items-center justify-center rounded-md p-2.5 text-gray-700">
					<span class="sr-only">Open main menu</span>
					<svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true" data-slot="icon">
						<path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" />
					</svg>
				</button>
			</div>
			<div class="hidden lg:flex lg:gap-x-12">
				<a href="/" class="text-sm font-semibold leading-6 text-blue-500">Accueil</a>

				<a href="/mes-projets" class="text-sm font-semibold leading-6 text-gray-900">Mes Projets</a>
				<a href="/mon-parcours" class="text-sm font-semibold leading-6 text-gray-900">Mon Parcours</a>
			</div>
			<div class="hidden lg:flex lg:flex-1 lg:justify-end gap-x-4">
				<svg xmlns="http://www.w3.org/2000/svg" width="2em" height="2em" viewBox="0 0 256 256" {...$$props} class="text-[#0a66c2] hover:opacity-75"
						 on:click={() => window.location.href = 'https://www.linkedin.com/in/romain-guillemot'} aria-label="Se rendre sur Linkedin" role="button" tabindex="0">
					<path fill="currentColor" d="M218.123 218.127h-37.931v-59.403c0-14.165-.253-32.4-19.728-32.4c-19.756 0-22.779 15.434-22.779 31.369v60.43h-37.93V95.967h36.413v16.694h.51a39.91 39.91 0 0 1 35.928-19.733c38.445 0 45.533 25.288 45.533 58.186zM56.955 79.27c-12.157.002-22.014-9.852-22.016-22.009s9.851-22.014 22.008-22.016c12.157-.003 22.014 9.851 22.016 22.008A22.013 22.013 0 0 1 56.955 79.27m18.966 138.858H37.95V95.967h37.97zM237.033.018H18.89C8.58-.098.125 8.161-.001 18.471v219.053c.122 10.315 8.576 18.582 18.89 18.474h218.144c10.336.128 18.823-8.139 18.966-18.474V18.454c-.147-10.33-8.635-18.588-18.966-18.453" />
				</svg>
				<svg xmlns="http://www.w3.org/2000/svg" width="2.06em" height="2em" viewBox="0 0 256 250" {...$$props} class="text-[#161614] hover:opacity-75"
						 on:click={() => window.location.href = 'https://github.com/Romain-GUILLEMOT'} aria-label="Se rendre sur GitHub" role="button" tabindex="0">
					<path fill="currentColor" d="M128.001 0C57.317 0 0 57.307 0 128.001c0 56.554 36.676 104.535 87.535 121.46c6.397 1.185 8.746-2.777 8.746-6.158c0-3.052-.12-13.135-.174-23.83c-35.61 7.742-43.124-15.103-43.124-15.103c-5.823-14.795-14.213-18.73-14.213-18.73c-11.613-7.944.876-7.78.876-7.78c12.853.902 19.621 13.19 19.621 13.19c11.417 19.568 29.945 13.911 37.249 10.64c1.149-8.272 4.466-13.92 8.127-17.116c-28.431-3.236-58.318-14.212-58.318-63.258c0-13.975 5-25.394 13.188-34.358c-1.329-3.224-5.71-16.242 1.24-33.874c0 0 10.749-3.44 35.21 13.121c10.21-2.836 21.16-4.258 32.038-4.307c10.878.049 21.837 1.47 32.066 4.307c24.431-16.56 35.165-13.12 35.165-13.12c6.967 17.63 2.584 30.65 1.255 33.873c8.207 8.964 13.173 20.383 13.173 34.358c0 49.163-29.944 59.988-58.447 63.157c4.591 3.972 8.682 11.762 8.682 23.704c0 17.126-.148 30.91-.148 35.126c0 3.407 2.304 7.398 8.792 6.14C219.37 232.5 256 184.537 256 128.002C256 57.307 198.691 0 128.001 0m-80.06 182.34c-.282.636-1.283.827-2.194.39c-.929-.417-1.45-1.284-1.15-1.922c.276-.655 1.279-.838 2.205-.399c.93.418 1.46 1.293 1.139 1.931m6.296 5.618c-.61.566-1.804.303-2.614-.591c-.837-.892-.994-2.086-.375-2.66c.63-.566 1.787-.301 2.626.591c.838.903 1 2.088.363 2.66m4.32 7.188c-.785.545-2.067.034-2.86-1.104c-.784-1.138-.784-2.503.017-3.05c.795-.547 2.058-.055 2.861 1.075c.782 1.157.782 2.522-.019 3.08m7.304 8.325c-.701.774-2.196.566-3.29-.49c-1.119-1.032-1.43-2.496-.726-3.27c.71-.776 2.213-.558 3.315.49c1.11 1.03 1.45 2.505.701 3.27m9.442 2.81c-.31 1.003-1.75 1.459-3.199 1.033c-1.448-.439-2.395-1.613-2.103-2.626c.301-1.01 1.747-1.484 3.207-1.028c1.446.436 2.396 1.602 2.095 2.622m10.744 1.193c.036 1.055-1.193 1.93-2.715 1.95c-1.53.034-2.769-.82-2.786-1.86c0-1.065 1.202-1.932 2.733-1.958c1.522-.03 2.768.818 2.768 1.868m10.555-.405c.182 1.03-.875 2.088-2.387 2.37c-1.485.271-2.861-.365-3.05-1.386c-.184-1.056.893-2.114 2.376-2.387c1.514-.263 2.868.356 3.061 1.403" />
				</svg>

			</div>
		</nav>
		{#if isOpen}

			<div class="lg:hidden" role="dialog" aria-modal="true">
				<div class="fixed inset-0 z-50"></div>
				<div class="fixed inset-y-0 right-0 z-50 w-full overflow-y-auto bg-white px-6 py-6 sm:max-w-sm sm:ring-1 sm:ring-gray-900/10">
					<div class="flex items-center justify-between">
						<a href="#" class="-m-1.5 p-1.5">
							<span class="sr-only">Logo Romain Guillemot</span>
							<img class="h-8 w-auto" src="/img/logo.png" alt="Logo Romain Guillemot">
						</a>
						<button type="button" class="-m-2.5 rounded-md p-2.5 text-gray-700" on:click={editDialog}>
							<span class="sr-only">Fermer le menu</span>
							<svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true" data-slot="icon">
								<path stroke-linecap="round" stroke-linejoin="round" d="M6 18 18 6M6 6l12 12" />
							</svg>
						</button>
					</div>
					<div class="mt-6 flow-root">
						<div class="-my-6 divide-y divide-gray-500/10">
							<div class="space-y-2 py-6">
								<a href="/" on:click={editDialog} class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-blue-500 hover:bg-gray-50">Accueil</a>

								<a href="/mes-projets" on:click={editDialog} class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50">Mes projets</a>
								<a href="/mon-parcours" on:click={editDialog} class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50">Mon parcours</a>

							</div>
							<div class="py-6 flex gap-x-4 justify-end">
								<svg xmlns="http://www.w3.org/2000/svg" width="2em" height="2em" viewBox="0 0 256 256" {...$$props} class="text-[#0a66c2] hover:opacity-75"
										 on:click={() => window.location.href = 'https://www.linkedin.com/in/romain-guillemot'} aria-label="Se rendre sur Linkedin" role="button" tabindex="0">
									<path fill="currentColor" d="M218.123 218.127h-37.931v-59.403c0-14.165-.253-32.4-19.728-32.4c-19.756 0-22.779 15.434-22.779 31.369v60.43h-37.93V95.967h36.413v16.694h.51a39.91 39.91 0 0 1 35.928-19.733c38.445 0 45.533 25.288 45.533 58.186zM56.955 79.27c-12.157.002-22.014-9.852-22.016-22.009s9.851-22.014 22.008-22.016c12.157-.003 22.014 9.851 22.016 22.008A22.013 22.013 0 0 1 56.955 79.27m18.966 138.858H37.95V95.967h37.97zM237.033.018H18.89C8.58-.098.125 8.161-.001 18.471v219.053c.122 10.315 8.576 18.582 18.89 18.474h218.144c10.336.128 18.823-8.139 18.966-18.474V18.454c-.147-10.33-8.635-18.588-18.966-18.453" />
								</svg>
								<svg xmlns="http://www.w3.org/2000/svg" width="2.06em" height="2em" viewBox="0 0 256 250" {...$$props} class="text-[#161614] hover:opacity-75"
										 on:click={() => window.location.href = 'https://github.com/Romain-GUILLEMOT'} aria-label="Se rendre sur GitHub" role="button" tabindex="0">
									<path fill="currentColor" d="M128.001 0C57.317 0 0 57.307 0 128.001c0 56.554 36.676 104.535 87.535 121.46c6.397 1.185 8.746-2.777 8.746-6.158c0-3.052-.12-13.135-.174-23.83c-35.61 7.742-43.124-15.103-43.124-15.103c-5.823-14.795-14.213-18.73-14.213-18.73c-11.613-7.944.876-7.78.876-7.78c12.853.902 19.621 13.19 19.621 13.19c11.417 19.568 29.945 13.911 37.249 10.64c1.149-8.272 4.466-13.92 8.127-17.116c-28.431-3.236-58.318-14.212-58.318-63.258c0-13.975 5-25.394 13.188-34.358c-1.329-3.224-5.71-16.242 1.24-33.874c0 0 10.749-3.44 35.21 13.121c10.21-2.836 21.16-4.258 32.038-4.307c10.878.049 21.837 1.47 32.066 4.307c24.431-16.56 35.165-13.12 35.165-13.12c6.967 17.63 2.584 30.65 1.255 33.873c8.207 8.964 13.173 20.383 13.173 34.358c0 49.163-29.944 59.988-58.447 63.157c4.591 3.972 8.682 11.762 8.682 23.704c0 17.126-.148 30.91-.148 35.126c0 3.407 2.304 7.398 8.792 6.14C219.37 232.5 256 184.537 256 128.002C256 57.307 198.691 0 128.001 0m-80.06 182.34c-.282.636-1.283.827-2.194.39c-.929-.417-1.45-1.284-1.15-1.922c.276-.655 1.279-.838 2.205-.399c.93.418 1.46 1.293 1.139 1.931m6.296 5.618c-.61.566-1.804.303-2.614-.591c-.837-.892-.994-2.086-.375-2.66c.63-.566 1.787-.301 2.626.591c.838.903 1 2.088.363 2.66m4.32 7.188c-.785.545-2.067.034-2.86-1.104c-.784-1.138-.784-2.503.017-3.05c.795-.547 2.058-.055 2.861 1.075c.782 1.157.782 2.522-.019 3.08m7.304 8.325c-.701.774-2.196.566-3.29-.49c-1.119-1.032-1.43-2.496-.726-3.27c.71-.776 2.213-.558 3.315.49c1.11 1.03 1.45 2.505.701 3.27m9.442 2.81c-.31 1.003-1.75 1.459-3.199 1.033c-1.448-.439-2.395-1.613-2.103-2.626c.301-1.01 1.747-1.484 3.207-1.028c1.446.436 2.396 1.602 2.095 2.622m10.744 1.193c.036 1.055-1.193 1.93-2.715 1.95c-1.53.034-2.769-.82-2.786-1.86c0-1.065 1.202-1.932 2.733-1.958c1.522-.03 2.768.818 2.768 1.868m10.555-.405c.182 1.03-.875 2.088-2.387 2.37c-1.485.271-2.861-.365-3.05-1.386c-.184-1.056.893-2.114 2.376-2.387c1.514-.263 2.868.356 3.061 1.403" />
								</svg>
							</div>
						</div>
					</div>
				</div>
			</div>
		{/if}

	</header>

	<div class="relative isolate overflow-hidden bg-gradient-to-b from-indigo-100/20 pt-14">
		<div class="absolute inset-y-0 right-1/2 -z-10 -mr-96 w-[200%] origin-top-right skew-x-[-30deg] bg-white shadow-xl shadow-indigo-600/10 ring-1 ring-indigo-50 sm:-mr-80 lg:-mr-96" aria-hidden="true"></div>
		<div class="mx-auto max-w-7xl px-6 py-32 sm:py-40 lg:px-8">
			<div class="mx-auto max-w-2xl lg:mx-0 lg:grid lg:max-w-none lg:grid-cols-2 lg:gap-x-16 lg:gap-y-6 xl:grid-cols-1 xl:grid-rows-1 xl:gap-x-8">
				<h1 class="max-w-2xl text-4xl font-bold tracking-tight text-gray-900 sm:text-6xl lg:col-span-2 xl:col-auto">Romain GUILLEMOT</h1>
				<div class="mt-6 max-w-xl lg:mt-0 xl:col-end-1 xl:row-start-1">
					<p class="text-lg leading-8 text-gray-600">
						Je m’appelle Romain, développeur informatique avec un intérêt particulier pour la gestion d’infrastructures et réseaux. Grâce à cette double compétence, je m’oriente naturellement vers le métier de DevOps, afin de réunir le développement et l’administration des systèmes au service des projets.
					</p>
					<div class="mt-10 flex items-center gap-x-6">
						<a href="/mes-projets" class=" rounded-md bg-blue-600 px-3.5 py-2.5 text-sm font-semibold text-white shadow-sm hover:bg-blue-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-blue-600">Mes projets</a>
						<a href="/mon-parcours" class="main-button group text-sm font-semibold leading-6 text-gray-900">
							Mon Parcours <span class="inline-block transition-transform group-hover:translate-x-2">→</span>
						</a>
					</div>
				</div>
				<img src="/img/main/main.png" alt="Romain GUILLEMOT" class="mt-10 aspect-[6/5] w-full max-w-lg rounded-2xl object-cover sm:mt-16 lg:mt-0 lg:max-w-none xl:row-span-2 xl:row-end-2 xl:mt-36">
			</div>
			{#if isVisible}

				<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 9 16" {...$$props}
						 class="bg-blue-600 rounded-full h-12 w-12 mx-auto mt-16 animate-bounce text-slate-200"
						 on:click={scrollToSkills}
						 aria-label="Navigate to skills section" role="button" tabindex="0"
						 transition:fly="{{ y: 20, duration: 300 }}">
					<path fill="currentColor" d="M4.5 13c-.28 0-.5-.22-.5-.5v-9c0-.28.22-.5.5-.5s.5.22.5.5v9c0 .28-.22.5-.5.5" />
					<path fill="currentColor" d="M4.5 14a.47.47 0 0 1-.35-.15l-3.5-3.5c-.2-.2-.2-.51 0-.71s.51-.2.71 0l3.15 3.15l3.15-3.15c.2-.2.51-.2.71 0s.2.51 0 .71l-3.5 3.5c-.1.1-.23.15-.35.15Z" />
				</svg>
			{/if}

		</div>

		<div class="absolute inset-x-0 bottom-0 -z-10 h-24 bg-gradient-to-t from-white sm:h-32"></div>

	</div>
</div>


<Projects/>

<Skills/>

<Github/>
