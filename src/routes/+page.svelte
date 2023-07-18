<script>
	import diverse_kids from '../images/home/home_diverse_kids.jpeg';
	import Header from '../components/header.svelte';
	import Footer from '../components/footer.svelte';
</script>

<div class="flex flex-col h-screen w-screen bg-yellow-100">
	<Header />
	<div class="flex flex-row bg-white pl-48 pr-48 pt-16 pb-32">
		<div class="flex flex-col w-1/2 pr-20">
			<h1 class="text-5xl font-bold pb-10">Empowering Students With Nutrition</h1>
			<h1 class="text-2xl pb-10">Simple and Engaging Nutrition Education</h1>
			<button
				class="flex rounded-md bg-primary justify-center items-center pb-3 pt-3 text-lg font-bold text-white"
			>
				Start Learning
			</button>
		</div>
		<div class="flex flex-col w-1/2 pl-20">
			<img class="rounded-lg" src={diverse_kids} alt="kids eating lunch" />
		</div>
	</div>
	<Footer />
</div>

<style lang="postcss">
</style>
