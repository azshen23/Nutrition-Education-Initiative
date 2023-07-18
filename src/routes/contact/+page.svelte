<script>
	import Header from '../../components/header.svelte';
	import Footer from '../../components/footer.svelte';
	import HappyKids from '../../images/contact/happynutritonkids.png';
</script>

<div class="flex flex-col h-screen w-screen">
	<Header />
	<div class="flex flex-col w-full pb-20">
		<div class="flex w-full items-center justify-center pt-20">
			<h1 class="font-bold text-5xl">Contact</h1>
		</div>
		<div class="flex flex-row pl-10 pr-10 lg:pl-48 lg:pr-48 pt-16 pb-32">
			<div class="flex flex-col w-full lg:w-1/2 lg:pr-20">
				<form class="flex flex-col">
					<label for="name" class="pt-5 pb-5 font-bold">Your Name</label>
					<input
						class="rounded-lg border-gray-300 border pt-4 pb-4 text-small font-thin pl-3"
						type="text"
						name="user_name"
						placeholder="Full Name"
					/>
					<label for="email" class="pt-10 pb-5 font-bold">Your Email</label>
					<input
						class="rounded-lg border-gray-300 border pt-4 pb-4 text-small font-thin pl-3"
						type="text"
						name="user_name"
						placeholder="youremail@gexample.com"
					/>
					<label for="subject" class="pt-10 pb-5 font-bold">Subject</label>
					<input
						class="rounded-lg border-gray-300 border pt-4 pb-4 text-small font-thin pl-3"
						type="text"
						name="user_name"
						placeholder="Subject"
					/>
					<label for="message" class="pt-10 pb-5 font-bold">Your Name</label>
					<textarea
						class="rounded-lg border-gray-300 border pt-4 pb-4 text-small font-thin pl-3"
						name="message"
						placeholder="Write Your Message Here"
					/>
					<input
						class="rounded-lg bg-primary hover:bg-accent cursor-pointer text-white pb-4 pt-4 mt-10 font-bold"
						type="button"
						value="Send Message"
					/>
				</form>
			</div>
			<div class="hidden lg:flex flex-col w-1/2 pt-10 pl-20">
				<img src={HappyKids} alt="happykids" class="rounded-2xl" />
			</div>
		</div>
	</div>

	<Footer />
</div>

<style lang="postcss">
</style>
