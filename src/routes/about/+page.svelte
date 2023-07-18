<script>
	import Header from '../../components/header.svelte';
	import Footer from '../../components/footer.svelte';
	import KidBanner from '../../images/about-us/parent-feeding-kid.jpg';

	import { onMount } from 'svelte';
	onMount(() => {
		document.querySelectorAll('a[href^="#"]').forEach((anchor) => {
			anchor.addEventListener('click', (e) => {
				e.preventDefault();

				// @ts-ignore
				const targetElement = document.querySelector(anchor.getAttribute('href'));
				// @ts-ignore
				targetElement.scrollIntoView({
					behavior: 'smooth'
				});
			});
		});
	});
</script>

<div class="flex flex-col h-screen w-screen">
	<Header />
	<div class="flex flex-col w-full">
		<div class="flex flex-row w-full pl-48 pr-48 pt-16 pb-32">
			<div class="flex flex-col w-full items-center">
				<h1 class="text-5xl font-bold pb-16">Who Are We?</h1>
				<p class="text-lg text-center pb-20">
					The Nutrition Education Initiative (NEI) is a medical student lead organization that was
					founded in 2020 with both an educational and research directed focus. The educational goal
					of NEI is to equip rural high school students with nutrition knowledge that will foster
					healthy eating behaviors beyond high school. The research goal of NEI is to examine
					attitude, behavioral, and knowledge changes through its education.
				</p>

				<img
					src={KidBanner}
					width="700"
					class="rounded-xl rounded-b-xl pb-20"
					alt="kid being fed"
				/>
				<a
					href="#mission"
					class="rounded-lg border-primary border bg-white text-accent text-xl pl-32 pr-32 pb-5 pt-5"
					>Learn more</a
				>
			</div>
		</div>
		<div class="flex flex-col w-full pb-32">
			<div class="flex flex-col w-full items-center">
				<h1 id="mission" class="text-5xl font-bold pt-40 pb-10">Our Mission</h1>
				<div class="flex flex-row justify-between w-full pl-12 pr-32">
					<div class="flex flex-col">
						<h1 class="text-3xl text-center pb-8">Empowering</h1>
						<p class="text-center">
							We believe in empowering students to make informed choices about their nutrition and
							overall health.
						</p>
					</div>
					<div class="flex flex-col">
						<h1 class="text-3xl text-center pb-8">Accessible</h1>
						<p class="text-center">
							N.E.I. provides accessible education to rural high school students, ensuring that
							everyone has the opportunity to learn about nutrition.
						</p>
					</div>
					<div class="flex flex-col">
						<h1 class="text-3xl text-center pb-8">Healthy Habits</h1>
						<p class="text-center">
							We promote healthy habits and encourage students to prioritize their well-being.
						</p>
					</div>
				</div>
			</div>
		</div>
	</div>

	<Footer />
</div>

<style lang="postcss">
</style>
