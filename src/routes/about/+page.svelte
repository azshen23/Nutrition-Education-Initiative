<script>
	import Header from '../../components/header.svelte';
</script>

<div class="flex flex-col h-screen w-screen bg-yellow-100">
	<Header />
	<div class="flex flex-row bg-red-400 pl-48 pr-48 pt-16 pb-32">
		<div class="flex flex-col w-1/2 pr-20">
			<h1 class="text-5xl font-bold pb-10">ABOUT US</h1>
			<h1 class="text-2xl pb-10">Simple and Engaging Nutrition Education</h1>
			<button
				class="flex rounded-md bg-white justify-center items-center pb-3 pt-3 text-lg font-bold"
			>
				Start Learning
			</button>
		</div>
	</div>
</div>

<style lang="postcss">
</style>