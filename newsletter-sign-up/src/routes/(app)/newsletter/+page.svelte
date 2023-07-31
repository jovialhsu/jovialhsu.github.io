<script>
	const lists = [
		'Product discovery and building what matters',
		'Measuring to ensure updates are a success',
		'And much more!'
	];
</script>

<svelte:head>
	<title>newsletter</title>
	<meta name="description" content="newsletter" />
</svelte:head>
<div class="flex flex-col">
	<!-- Sign-up form start -->
	<div class="w-full">
		<img class="w-full" src="/assets/images/illustration-sign-up-mobile.svg" alt="" />
	</div>
	<div class="px-6">
		<h1 class="text-4xl mt-6 mb-4 font-robotoBold">Stay updated!</h1>

		<p class="my-4">Join 60,000+ product managers receiving monthly updates on:</p>
		<ul class="list-image-[url(assets/images/icon-list.svg)] ml-6">
			{#each lists as list}
				<li class="my-4">{list}</li>
			{/each}
		</ul>
		<label class="font-robotoBold text-xs block" for="">Email address </label>
		<input
			class="border rounded-lg py-5 mt-2 mb-6 w-full placeholder:pl-6"
			type="text"
			placeholder="email@company.com"
		/>
		<button type="submit" class="py-5 text-white bg-blue-950 w-full rounded-lg font-robotoBold"
			>Subscribe to monthly newsletter</button
		>
	</div>
	<!-- Sign-up form end -->

	<!-- Success message start -->
	<div class="px-6">
		<h1 class="text-4xl mt-6 mb-4 font-robotoBold">Thanks for subscribing!</h1>
		<p class="mb-8">
			A confirmation email has been sent to <span class="font-bold"> ash@loremcompany.com.</span> Please
			open it and click the button inside to confirm your subscription.
		</p>
		<button class="py-5 text-white bg-blue-950 w-full rounded-lg font-robotoBold"
			>Dismiss message</button
		>
	</div>
	<!-- Success message end -->
</div>
