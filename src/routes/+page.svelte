<script>
	import diverse_kids from '../images/home/home_diverse_kids.jpeg';
	import Header from '../components/header.svelte';
	import Footer from '../components/footer.svelte';
	import { Splide, SplideSlide } from '@splidejs/svelte-splide';
	import '@splidejs/svelte-splide/css';
	import '@splidejs/svelte-splide/css/skyblue';
	import '@splidejs/svelte-splide/css/sea-green';
	import '@splidejs/svelte-splide/css/core';
	import quote from '../images/home/quote.png';
	import person1 from '../images/home/1.png';
	import jeoparody from '../images/home/jeoparody.png';
	import nutrition from '../images/home/nutritionppt.png';

	const testimonials = [
		'Having the Nutrition Initiative join our high school as "outsiders" was an absolute breath of fresh air! It was an incredibly valuable experience for our students to have professionals from outside the school environment engage with them on the topic of nutrition. ',
		'As teachers, we see our students every day and sometimes it can be challenging to introduce new perspectives and ideas. The Nutrition Initiative brought a vibrant energy and a wealth of knowledge to our school.',
		' Their presence created an exciting atmosphere that motivated and inspired our students to take a closer look at their eating habits. ',
		"It was truly refreshing to witness the students' enthusiasm as they interacted with these professionals who had a different approach and a unique way of presenting the importance of healthy eating.",
		'The engagement level was through the roof, and it was evident that our students appreciated the chance to interact with these knowledgeable professionals in a different setting. We hope to have more opportunities like this in the future to keep our educational environment vibrant and exciting!',
		"Having medical students join my physical education classroom was a game-changer!  The medical students' expertise and passion for nutrition were evident as they went beyond the basics, exploring the science behind healthy eating and dispelling common misconceptions.",
		'Their fresh perspective and dedication enriched our physical education curriculum, and I look forward to future collaborations!',
		' Our students were eagerly engaged in discussions on how nutrition impacts athletic performance, body composition, and overall well-being. I am grateful for the opportunity to collaborate with these passionate medical students.',
		"Their fresh perspective and wealth of knowledge on healthy eating behaviors impressed me. They seamlessly integrated topics like creatine, social media, and nutrition label literacy into their lessons, captivating our students' attention and curiosity."
	];

	const quoteAuthor = [
		'Teacher at Mount Pleasant High School',
		'Teacher at Mount Pleasant High School',
		'Teacther at Beal City High School',
		'Teacher at Mount Pleasant High School',
		'Teacther at Beal City High School',
		'Teacher at Mount Pleasant High School',
		'Teacther at Beal City High School',
		'Teacther at Beal City High School',
		'Teacher at Mount Pleasant High School'
	];

	function downloadPowerpoint() {
		const downloadLink = document.createElement('a');
		downloadLink.href = 'src/downloads/jeoparody.pptx'; // Path to your PowerPoint file
		downloadLink.download = 'jeoparody.pptx'; // Desired download filename
		downloadLink.style.display = 'none';
		document.body.appendChild(downloadLink);
		downloadLink.click();
		document.body.removeChild(downloadLink);
	}
</script>

<div class="flex flex-col h-screen w-full">
	<Header />
	<div
		class="flex flex-col lg:flex-row bg-white pl-5 pr-5 lg:pl-20 lg:pr-20 lg:pl-48 lg:pr-48 pt-32 pb-32"
	>
		<div class="flex flex-col w-full justify-center lg:w-1/2 lg:pr-20">
			<div>
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
		</div>
		<div class="flex flex-col w-full lg:w-1/2 pt-20 lg:pt-0 lg:pl-20">
			<img class="rounded-lg" src={diverse_kids} alt="kids eating lunch" />
		</div>
	</div>
	<div class="flex flex-col w-full pt-20 pb-40">
		<h1 class="text-center text-4xl font-semibold text-lime-700 pb-5">Testimonials</h1>
		<h1 class="text-center text-lg pb-10">What people are saying about us...</h1>
		<div class="flex flex-row w-full md:pl-20 md:pr-10">
			<div class="hidden: md:flex flex-col w-[35%] items-center justify-center">
				<img src={person1} alt="classroom" class="rounded-2xl w-4/5" />
			</div>
			<div class="flex flex-col w-full md:w-[65%] items-center">
				<div class="flex flex-col w-full md:w-5/6">
					<Splide
						options={{
							gap: '1rem',
							padding: '5rem',
							perPage: 2,
							breakpoints: {
								1480: {
									perPage: 1,
									padding: '0rem'
								}
							}
						}}
					>
						{#each testimonials as testimonial, i}
							<SplideSlide>
								<div
									class={`w-full h-full border rounded-2xl pt-10 pb-20 pl-10 pr-10
									 font-medium flex flex-col items-center justify-center ${
											i % 2 === 0 ? 'bg-secondary' : 'bg-primary'
										}`}
								>
									<div class="flex w-full pb-5"><img src={quote} alt="quote" class="w-12" /></div>

									<h1>{testimonial}</h1>
									<h1 class="text-start w-full pt-10">-{quoteAuthor[i]}</h1>
								</div>
							</SplideSlide>
						{/each}
					</Splide>
				</div>
			</div>
		</div>
	</div>
	<div class="flex flex-col w-full items-center text-center">
		<h1 class="font-bold text-4xl">Take a look at our curriculum here</h1>
		<div class="flex flex-col lg:flex-row lg:pl-20 lg:pr-20 pb-40 w-3/4 pt-20">
			<div class="flex flex-col w-full lg:w-1/2 items-center">
				<img src={jeoparody} alt="jeaparody" class="rounded-2xl w-3/4" />
				<div class="pt-5" />
				<button
					class="flex rounded-md bg-primary hover:bg-accent cursor-pointer justify-center items-center p-3 text-lg font-bold text-white"
					on:click={downloadPowerpoint}>Download Here</button
				>
			</div>
			<div class="pt-5 flex lg:hidden" />
			<div class="flex flex-col w-full lg:w-1/2 items-center">
				<img src={nutrition} alt="jeaparody" class="rounded-2xl" />
				<div class="pt-5" />
				<button
					class="flex rounded-md bg-primary hover:bg-accent cursor-pointer justify-center items-center p-3 text-lg font-bold text-white"
					>Download Here</button
				>
			</div>
		</div>
	</div>

	<Footer />
</div>

<style lang="postcss">
</style>
