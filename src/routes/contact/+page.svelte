<script>
	import Header from '../../components/header.svelte';
</script>

<div class="flex flex-col h-screen w-screen bg-yellow-100">
	<Header />
	<div class="flex flex-row bg-red-400 pl-48 pr-48 pt-16 pb-32">
		<div class="flex flex-col w-1/2 pr-20">
			<form>
				<label for="name">Name</label>
				<input type="text" name="user_name" />
				<label for="email">Email</label>
				<input type="email" name="user_email" />
				<label for="message">Message</label>
				<textarea name="message" />
				<input type="submit" value="Send" />
			</form>
		</div>
	</div>
</div>

<style lang="postcss">
</style>
