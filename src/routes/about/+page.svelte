<script>
	import Header from '../../components/header.svelte';
	import Footer from '../../components/footer.svelte';
	import example1 from '../../images/about-us/example1.png';
	import Board1 from '../../images/about-us/president.jpeg';
	import Board2 from '../../images/about-us/MaxVerbruggeHeadshot.png';
	import Board3 from '../../images/about-us/DanielleCalimente.png';
	import Board4 from '../../images/about-us/ElizabethDarga.png';
	import MtPleasant1 from '../../images/about-us/JamesChung.png';
	import MtPleasant2 from '../../images/about-us/SimoneRhodes.png';

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

	const boardList = [
		{
			name: 'Nathan Shen',
			img: Board1
		},
		{
			name: 'Max Verbrugge',
			img: Board2
		},
		{
			name: 'Danielle Calimente',
			img: Board3
		},
		{
			name: 'Elizabeth Darga',
			img: Board4
		}
	];

	const mtPleasantBoardList = [
		{
			name: 'James Chung',
			img: MtPleasant1
		},
		{
			name: 'Simone Rhodes',
			img: MtPleasant2
		}
	];
</script>

<div class="flex flex-col h-screen w-full m-0 p-0">
	<Header />
	<div class="flex flex-col w-full">
		<div class="flex flex-row w-full pl-10 pr-10 pt-16 pb-32">
			<div class="flex flex-col w-full items-center">
				<h1 class="text-5xl font-bold pb-16 text-center">Who Are We?</h1>
				<div class="flex flex-col lg:flex-row w-full items-center justify-center pb-40">
					<div class="flex flex-col w-full lg:w-1/3 items-center">
						<img src={example1} alt="Example1" class="w-96 rounded-2xl opacity-0" />
					</div>
					<div class="flex flex-col w-full lg:w-1/2 items-center justify-center">
						<p
							class="text-xl font-medium text-center md:text-start md:pb-20 lg:pr-60 md:pr-20 md:pl-20 pt-20 lg:pt-0"
						>
							The Nutrition Education Initiative (NEI) is a medical student lead organization that
							was founded in 2020 with both an educational and research directed focus. The
							educational goal of NEI is to equip rural high school students with nutrition
							knowledge that will foster healthy eating behaviors beyond high school. The research
							goal of NEI is to examine attitude, behavioral, and knowledge changes through its
							education.
						</p>
					</div>
				</div>

				<a
					href="#mission"
					class="rounded-lg border-primary border-2 font-bold bg-white text-accent text-xl pl-20 pr-20 lg:pl-32 lg:pr-32 pb-5 pt-5"
					>Learn more</a
				>
			</div>
		</div>
		<div class="flex flex-col w-full pb-32">
			<div class="flex flex-col w-full items-center">
				<h1 id="mission" class="text-5xl font-bold pt-10 pb-20">Our Mission</h1>
				<div class="flex md:flex-row flex-col w-full pl-10 pr-10 lg:pl-32 lg:pr-32 gap-8">
					<div class="flex-1 flex-col rounded-2xl bg-secondary pb-20 pt-10 pl-5 pr-5">
						<h1 class="text-3xl text-center pb-8">Empowering</h1>
						<p class="text-center">
							We believe in empowering students to make informed choices about their nutrition and
							overall health.
						</p>
					</div>
					<div class="flex-1 flex-col rounded-2xl bg-primary pb-20 pt-10 pl-5 pr-5">
						<h1 class="text-3xl text-center pb-8">Accessible</h1>
						<p class="text-center">
							N.E.I. provides accessible education to rural high school students, ensuring that
							everyone has the opportunity to learn about nutrition.
						</p>
					</div>
					<div class="flex-1 flex-col rounded-2xl bg-secondary pb-20 pt-10 pl-5 pr-5">
						<h1 class="text-3xl text-center pb-8">Healthy Habits</h1>
						<p class="text-center">
							We promote healthy habits and encourage students to prioritize their well-being.
						</p>
					</div>
				</div>
			</div>
		</div>
		<div
			class="flex flex-row w-full pl-10 pr-10 lg:pl-48 lg:pr-48 pt-16 pb-32 text-center lg:text-left"
		>
			<div class="flex flex-col w-full items-center">
				<h1 class="text-5xl font-bold pb-16">Why are we here?</h1>
				<p class="text-lg text-center pb-20">
					The NEI was initiated to address the rising obesity rates, and related obesity sequelae
					such as stroke, heart disease, diabetes, and cancer. Obesity is a multifactorial disorder
					and requires a multidisciplinary approach in combating its epidemic. To date, the NEI has
					supplied over 20 hours of free nutrition education to the Mount Pleasant and Beal City
					Public Schools and plans to expand to neighboring rural high schools. The NEI currently
					has an IRB approved study that will examine if high school student behaviors will change
					after the intervention. The NEI has three medical school faculty advisors who have
					provided oversight over current research: Dr. Ariel Cascio, Dr. Jesse Bakke, and Dr.
					Samantha Hahn. Nathan Shen, a current M3 medical student, has currently led the NEI with
					support of fellow medical students.
				</p>
			</div>
		</div>
		<div class="flex flex-row w-full pb-32">
			<div class="flex flex-col w-full pl-5 pr-5 lg:pl-20 lg:pr-20">
				<h1 class="text-5xl font-bold pb-16 text-center">Meet our board of directors!</h1>
				<div
					class="grid grid-cols-1 md:grid-cols-2 xl:grid-cols-3 gap-y-4 lg:flex-row w-full items-center text-center"
				>
					{#each boardList as boardMember, i}
						<div class="flex-1 flex-col">
							<div class="flex items-center justify-center pb-5">
								<img src={boardMember.img} alt="President" class="w-80 h-80 rounded-3xl" />
							</div>
							<h1 class="text-2xl text-center pb-4">{boardMember.name}</h1>
						</div>
					{/each}
				</div>
			</div>
		</div>
		<div class="flex flex-row w-full pb-32">
			<div class="flex flex-col w-full pl-5 pr-5 lg:pl-20 lg:pr-20">
				<h1 class="text-3xl font-bold pb-16 text-center">Mt. Pleasant Branch Leaders</h1>
				<div
					class="grid grid-cols-1 md:grid-cols-2 xl:grid-cols-3 gap-y-4 lg:flex-row w-full items-center text-center"
				>
					{#each mtPleasantBoardList as boardMember, i}
						<div class="flex-1 flex-col">
							<div class="flex items-center justify-center pb-5">
								<img src={boardMember.img} alt="President" class="w-80 h-80 rounded-3xl" />
							</div>
							<h1 class="text-2xl text-center pb-4">{boardMember.name}</h1>
						</div>
					{/each}
				</div>
			</div>
		</div>
	</div>

	<Footer />
</div>

<style lang="postcss">
</style>
