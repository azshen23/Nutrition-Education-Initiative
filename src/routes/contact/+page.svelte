<script>
	import Header from '../../components/header.svelte';
	import Footer from '../../components/footer.svelte';
</script>

<div class="flex flex-col h-screen w-screen">
	<Header />
	<div class="flex flex-row pl-48 pr-48 pt-16 pb-32">
		<div class="flex flex-col w-1/2 pr-20">
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
			</form>
		</div>
	</div>
	<Footer />
</div>

<style lang="postcss">
</style>
