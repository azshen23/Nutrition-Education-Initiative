<script>
	import { fade } from 'svelte/transition';
	import { onMount } from 'svelte';

	let showPopup = false;

	function togglePopup() {
		showPopup = !showPopup;
	}

	onMount(() => {
		// @ts-ignore
		function handleOutsideClick(event) {
			if (!event.target.closest('.popup-container') && !event.target.closest('.toggle-button')) {
				showPopup = false;
			}
		}

		// @ts-ignore
		document.addEventListener('click', handleOutsideClick);

		return () => {
			document.removeEventListener('click', handleOutsideClick);
		};
	});
</script>

<div class="flex flex-col justify-between items-center pt-20 pb-10 border-t bg-white">
	<h1 class="text-5xl font-bold pb-20">Start Your Nutrition Journey</h1>

	<button
		class="rounded-lg border-2 border-primary text-primary font-bold pl-10 pr-10 pb-5 pt-5"
		on:click|stopPropagation={togglePopup}
	>
		Enter your email to receive updates<button />
	</button>

	{#if showPopup}
		<div
			transition:fade
			class="fixed top-0 left-0 w-full h-full bg-gray-900 bg-opacity-50 flex justify-center items-center"
		>
			<div class="bg-white rounded pl-40 pr-40 pb-10 pt-10 popup-container relative">
				<button
					class="absolute top-2 right-2 text-gray-500 hover:text-gray-700"
					on:click={togglePopup}
				>
					<svg
						xmlns="http://www.w3.org/2000/svg"
						class="h-5 w-5"
						viewBox="0 0 20 20"
						fill="currentColor"
					>
						<path
							fill-rule="evenodd"
							d="M3.646 3.646a.5.5 0 01.708 0L10 9.293l5.646-5.647a.5.5 0 01.708.708L10.707 10l5.647 5.646a.5.5 0 01-.708.708L10 10.707l-5.646 5.647a.5.5 0 01-.708-.708L9.293 10 3.646 4.354a.5.5 0 010-.708z"
							clip-rule="evenodd"
						/>
					</svg>
				</button>
				<h1 class="text-2xl font-bold pb-10">Join Our Mailing List Today To Recieve Updates!</h1>
				<input
					type="email"
					placeholder="Email address"
					class="w-full p-2 pr-40 border rounded mb-4"
				/>
				<div class="flex row">
					<button
						class="pb-4 pt-4 bg-primary w-full text-white rounded hover:bg-accent"
						on:click={togglePopup}
					>
						Subscribe!
					</button>
				</div>
			</div>
		</div>
	{/if}
</div>

<style lang="postcss">
</style>
