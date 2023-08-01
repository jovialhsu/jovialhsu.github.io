<script>
	const lists = [
		'Product discovery and building what matters',
		'Measuring to ensure updates are a success',
		'And much more!'
	];
	let success = true;
</script>

<svelte:head>
	<title>newsletter</title>
	<meta name="description" content="newsletter" />
</svelte:head>
<div class="flex flex-col sm:flex-row sm:justify-center sm:mt-[20vh]">
	{#if success === false}
		<!-- Sign-up form start -->
		<div class="sm:order-2 sm:ml-4">
			<div
				class="w-full sm:w-[400px] h-[200px] sm:rounded-2xl sm:h-full bg-cover bg-center sm:bg-[url('/assets/images/illustration-sign-up-desktop.svg')] bg-[url('/assets/images/illustration-sign-up-mobile.svg')]"
			/>
		</div>
		<div class="px-6 sm:order-1">
			<h1 class="text-4xl mt-6 mb-4 font-robotoBold">Stay updated!</h1>

			<p class="my-4">Join 60,000+ product managers receiving monthly updates on:</p>
			<ul class="list-image-[url(assets/images/icon-list.svg)] ml-6">
				{#each lists as list}
					<li class="my-4">{list}</li>
				{/each}
			</ul>
			<div class="relative">
				<label class="font-robotoBold text-xs inline-block" for="">Email address </label>

				<input
					class="peer invalid:border-red-500 invalid:text-red-400 invalid:bg-red-100 border rounded-lg py-5 mt-2 pl-6 mb-6 w-full before before:content-['Valid email required'] before:block before:text-red-500"
					type="email"
					placeholder="email@company.com"
				/>
				<span
					class="invisible peer-invalid:visible peer-invalid:top-0 peer-invalid:opacity-100 opacity-10 text-xs absolute top-14 right-0 transition-all font-robotoBold text-red-400"
					>Valid email required</span
				>
				<button
					type="submit"
					class="py-5 text-white bg-blue-950 w-full peer-invalid:disabled rounded-lg font-robotoBold hover:bg-gradient-to-r from-red-500 to-orange-500 shadow-2x hover:shadow]"
					on:click|preventDefault={() => {
						success = true;
					}}>Subscribe to monthly newsletter</button
				>
			</div>
		</div>

		<!-- Sign-up form end -->
	{:else}
		<!-- Success message start -->
		<div class="px-6 sm:w-[40%]">
			<div class="bg-[url('/assets/images/icon-success.svg')] w-[70px] h-[70px] bg-cover" />
			<h1 class="text-4xl sm:text-6xl mt-6 mb-4 font-robotoBold">Thanks for subscribing!</h1>
			<p class="mb-8">
				A confirmation email has been sent to <span class="font-bold"> ash@loremcompany.com.</span> Please
				open it and click the button inside to confirm your subscription.
			</p>
			<button
				class="py-5 text-white bg-blue-950 w-full rounded-lg font-robotoBold hover:bg-gradient-to-r from-red-500 to-orange-500 shadow-2xl hover:shadow"
				on:click|preventDefault={() => {
					success = false;
				}}>Dismiss message</button
			>
		</div>
	{/if}
	<!-- Success message end -->
</div>
