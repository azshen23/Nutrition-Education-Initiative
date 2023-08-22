<script>
	import Header from '../../components/header.svelte';
	import Footer from '../../components/footer.svelte';
	import HappyKids from '../../images/contact/happynutritonkids.png';
	import { afterUpdate } from 'svelte';

	const contactInfo = {
		number: '+1 (734) 238-3067',
		email: 'NutritionEducationInitiative@gmail.com'
	};
	let name = '';
	let email = '';
	let subject = '';
	let message = '';

	let isNameValid = true;
	let isEmailValid = true;
	let isSubjectValid = true;
	let isMessageValid = true;

	let isSubmitted = false;
	let isSubmitError = false;

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
		if (isNameValid && isEmailValid && isSubjectValid && isMessageValid) {
			fetch('https://api.emailjs.com/api/v1.0/email/send', {
				method: 'POST',
				headers: {
					'Content-Type': 'application/json'
					// Add any other headers if needed
				},
				body: JSON.stringify(data)
			})
				.then((response) => {
					if (response.ok) {
						console.log('success', response);
						name = '';
						email = '';
						subject = '';
						message = '';
						isSubmitted = true;
					} else {
						throw new Error(response.statusText);
					}
				})
				.catch((error) => {
					console.log('Error:', error);
				});
		}
	}
	$: {
		isNameValid = true;
		isEmailValid = true;
		isSubjectValid = true;
		isMessageValid = true;
	}
</script>

<div class="flex flex-col h-screen w-full">
	<Header />
	<div class="flex flex-col w-full pb-20">
		<div class="flex w-full items-center justify-center pt-20">
			<h1 class="font-bold text-5xl">Contact</h1>
		</div>
		<div class="flex flex-row pl-10 pr-10 lg:pl-48 lg:pr-48 pt-16 pb-24">
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
			{#if isSubmitted}
				<div class="fixed inset-0 flex items-center justify-center z-50">
					<div class="bg-white rounded-lg p-8 shadow-lg">
						<h2 class="text-2xl font-bold mb-4">Success!</h2>
						<p>Your message has been submitted successfully.</p>
						<button
							class="mt-6 bg-primary hover:bg-accent text-white font-bold py-2 px-4 rounded-lg"
							on:click={() => (isSubmitted = false)}>Close</button
						>
					</div>
				</div>
			{/if}
			<div class="hidden lg:flex flex-col w-1/2 pt-10 pl-20">
				<img src={HappyKids} alt="happykids" class="rounded-2xl" />
			</div>
		</div>
	</div>
	<div class="flex flex-col w-full pb-40 items-center">
		<div
			class="flex flex-col lg:flex-row w-full lg:w-3/5 rounded-lg bg-gray-200 pl-20 pr-20 pb-16 pt-16 justify-between"
		>
			<div class="flex flex-col">
				<h1 class="text-center font-bold text-xl pb-2 lg:pb-5">Call us</h1>
				<h2 class="text-center text-lg pb-6 lg:pb-0">{contactInfo.number}</h2>
			</div>
			<div class="flex flex-col">
				<h1 class="text-center font-bold text-xl pb-2 lg:pb-5">Email Us</h1>
				<h2 class="text-center text-lg pb-6 lg:pb-0">{contactInfo.email}</h2>
			</div>
		</div>
	</div>

	<Footer />
</div>

<style lang="postcss">
</style>
