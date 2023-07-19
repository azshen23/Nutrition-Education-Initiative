<script>
	import logoNoBg from '../images/svg/logo-no-background.svg';
	import { onMount } from 'svelte';
	import { fade } from 'svelte/transition';

	let showMenu = false;

	onMount(() => {
		const toggleButton = document.getElementById('toggleButton');
		const menuLinks = document.getElementById('menuLinks');

		// @ts-ignore
		toggleButton.addEventListener('click', () => {
			showMenu = !showMenu;
		});
	});
</script>

<div>
	<div class="sm:hidden">
		<div class="flex flex-col items-center py-4 bg-white border-b">
			<div class="flex justify-between items-center w-full px-4">
				<a href="/">
					<img src={logoNoBg} alt="NEI logo" width="150" height="150" />
				</a>
				<button id="toggleButton" class="text-xl focus:outline-none">
					<svg class="h-6 w-6 text-gray-600" fill="none" viewBox="0 0 24 24" stroke="currentColor">
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M4 6h16M4 12h16M4 18h16"
						/>
					</svg>
				</button>
			</div>
			{#if showMenu}
				<div
					id="menuLinks"
					class="flex flex-col items-center w-full px-4 mt-4 space-y-4"
					transition:fade
				>
					<a class="text-xl" href="/">Home</a>
					<a class="text-xl" href="/about">About us</a>
					<a class="text-xl" href="/contact">Contact</a>
					<a class="text-xl" href="/donate">Donate</a>
				</div>
			{/if}
		</div>
	</div>
	<div
		class="hidden sm:flex flex-row justify-between items-center pl-20 pr-20 pt-5 pb-5 bg-white border-b"
	>
		<a href="/">
			<img src={logoNoBg} alt="NEI logo" width="150" height="150" />
		</a>
		<a class="text-xl" href="/">Home</a>
		<a class="text-xl" href="/about">About us</a>
		<a class="text-xl" href="/contact">Contact</a>
		<a class="text-xl" href="/donate">Donate</a>
	</div>
</div>

<style lang="postcss">
</style>
