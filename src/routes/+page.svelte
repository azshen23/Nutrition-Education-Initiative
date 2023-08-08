<script>
	import diverse_kids from '../images/home/home_diverse_kids.jpeg';
	import Header from '../components/header.svelte';
	import Footer from '../components/footer.svelte';
</script>

<div class="flex flex-col h-screen w-full">
	<Header />
	<div
		class="flex flex-col lg:flex-row bg-white pl-5 pr-5 lg:pl-20 lg:pr-20 lg:pl-48 lg:pr-48 pt-32 pb-32"
	>
		<div class="flex flex-col w-full lg:w-1/2 lg:pr-20">
			<h1 class="text-5xl font-bold pb-10 text-center lg:text-left">
				Empowering Students With Nutrition
			</h1>
			<h1 class="text-2xl pb-10 text-center lg:text-left">
				Simple and Engaging Nutrition Education
			</h1>
			<a
				class="flex rounded-md bg-primary hover:bg-accent cursor-pointer justify-center items-center pb-3 pt-3 text-lg font-bold text-white"
				href="/about"
			>
				Start Learning
			</a>
		</div>
		<div class="flex flex-col w-full lg:w-1/2 pt-20 lg:pt-0 lg:pl-20">
			<img class="rounded-lg" src={diverse_kids} alt="kids eating lunch" />
		</div>
	</div>
	<Footer />
</div>

<style lang="postcss">
</style>
