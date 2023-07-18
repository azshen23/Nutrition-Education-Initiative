<script>
	import Header from '../../components/header.svelte';
	import Footer from '../../components/footer.svelte';
	import HappyKids from '../../images/contact/happynutritonkids.png';
	import { afterUpdate } from 'svelte';

	let name = '';
	let email = '';
	let subject = '';
	let message = '';

	let isNameValid = true;
	let isEmailValid = true;
	let isSubjectValid = true;
	let isMessageValid = true;

	function handleSubmit() {
		// Reset validation state
		isNameValid = true;
		isEmailValid = true;
		isSubjectValid = true;
		isMessageValid = true;

		// Perform form validation
		if (name.trim() === '') {
			isNameValid = false;
		}
		if (email.trim() === '') {
			isEmailValid = false;
		}
		if (subject.trim() === '') {
			isSubjectValid = false;
		}
		if (message.trim() === '') {
			isMessageValid = false;
		}
		var data = {
			service_id: 'service_21cxrbi',
			template_id: 'template_sflz257',
			user_id: '9-edHskMveIOzuhYE',
			template_params: {
				name: name,
				email: email,
				subject: subject,
				message: message
			}
		};
		console.log(data);
		fetch('https://api.emailjs.com/api/v1.0/email/send', {
			method: 'POST',
			headers: {
				'Content-Type': 'application/json'
				// Add any other headers if needed
			},
			body: JSON.stringify(data)
		})
			.then((response) => response.json())
			.then((data) => {
				console.log('success', data);
			})
			.catch((error) => {
				console.log(error);
			});
		// Clear validation indications when fields change
		afterUpdate(() => {
			isNameValid = true;
			isEmailValid = true;
			isSubjectValid = true;
			isMessageValid = true;
		});
	}
</script>

<div class="flex flex-col h-screen w-screen">
	<Header />
	<div class="flex flex-col w-full pb-20">
		<div class="flex w-full items-center justify-center pt-20">
			<h1 class="font-bold text-5xl">Contact</h1>
		</div>
		<div class="flex flex-row pl-10 pr-10 lg:pl-48 lg:pr-48 pt-16 pb-32">
			<div class="flex flex-col w-full lg:w-1/2 lg:pr-20">
				<form class="flex flex-col" on:submit|preventDefault={handleSubmit}>
					<label for="name" class="pt-5 pb-5 font-bold">Your Name</label>
					<input
						class="rounded-lg border-gray-300 border pt-4 pb-4 text-small font-thin pl-3"
						type="text"
						id="name"
						name="user_name"
						autocomplete="name"
						placeholder="Full Name"
						bind:value={name}
					/>
					{#if !isNameValid}
						<p class="text-red-500">*Name is required</p>
					{/if}
					<label for="email" class="pt-10 pb-5 font-bold">Your Email</label>
					<input
						class="rounded-lg border-gray-300 border pt-4 pb-4 text-small font-thin pl-3"
						type="text"
						id="email"
						name="user_name"
						autocomplete="email"
						placeholder="youremail@gexample.com"
						bind:value={email}
					/>
					{#if !isEmailValid}
						<p class="text-red-500">*Email is required</p>
					{/if}
					<label for="subject" class="pt-10 pb-5 font-bold">Subject</label>
					<input
						class="rounded-lg border-gray-300 border pt-4 pb-4 text-small font-thin pl-3"
						type="text"
						id="subject"
						name="user_name"
						placeholder="Subject"
						bind:value={subject}
					/>
					{#if !isSubjectValid}
						<p class="text-red-500">*Subject is required</p>
					{/if}
					<label for="message" class="pt-10 pb-5 font-bold">Message</label>
					<textarea
						class="rounded-lg border-gray-300 border pt-4 pb-4 text-small font-thin pl-3"
						name="message"
						id="message"
						placeholder="Write Your Message Here"
						bind:value={message}
					/>
					{#if !isMessageValid}
						<p class="text-red-500">*Message is required</p>
					{/if}
					<input
						class="rounded-lg bg-primary hover:bg-accent cursor-pointer text-white pb-4 pt-4 mt-10 font-bold"
						type="submit"
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
