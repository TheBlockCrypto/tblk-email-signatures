<script lang="ts">
	const fields = {
		name: 'Josh Gragg',
		title: 'Head of Design',
		number: '555-666-1337',
		location: 'Colorado Springs, CO (MDT)',
    personalTwitter: '',
    personalTelegram: '',

		twitter: 'https://twitter.com/TheBlock__',
		linkedin: 'https://linkedin.com/company/theblockcrypto/',
		telegram: 'https://t.me/theblock',
		link: 'https://www.theblock.co/'
	};

	let signatureElement: HTMLElement;
	let successMessage = false;
	$: buttonText = successMessage ? 'Copied!' : 'Copy Signature';

	import Signature from '$lib/components/Signature.svelte';
	import { fly } from 'svelte/transition';

	function copySignature() {
		successMessage = true;
		setTimeout(() => {
			successMessage = false;
		}, 1500);
		navigator.clipboard.write([
			new ClipboardItem({
				'text/plain': new Blob([signatureElement.innerText], { type: 'text/plain' }),
				'text/html': new Blob([signatureElement.innerHTML], { type: 'text/html' })
			})
		]);
	}
</script>

<div>
	<div class="flex gap-12 p-4 justify-center border-2 bg-slate-50 border-slate-50 shadow-md w-auto">
		<div class="personal flex items-end flex-col gap-3">
			<h1 class="mr-auto text-2xl font-bold">Personal Information</h1>

			<div class="flex flex-col gap-2" transition:fly={{ x: 100, duration: 350 }}>
				<label class="font-medium" for="name"> Display Name </label>
				<input
					class="shadow-md focus:outline-none focus:border-2 focus:border-violet-500 focus:shadow-sm focus:shadow-violet-300 py-2 px-3 w-72"
					name="name"
					bind:value={fields.name}
				/>
			</div>

			<div class="flex flex-col gap-2" transition:fly={{ x: 100, duration: 350 }}>
				<label class="font-medium" for="title"> Job Title </label>
				<input
					class="shadow-md focus:outline-none focus:border-2 focus:border-violet-500 focus:shadow-sm focus:shadow-violet-300 py-2 px-3 w-72"
					name="title"
					bind:value={fields.title}
				/>
			</div>

			<div class="flex flex-col gap-2" transition:fly={{ x: 100, duration: 350 }}>
				<label class="font-medium" for="number"> Phone Number (Optional) </label>
				<input
					class="shadow-md focus:outline-none focus:border-2 focus:border-violet-500 focus:shadow-sm focus:shadow-violet-300 py-2 px-3 w-72"
					name="number"
					bind:value={fields.number}
				/>
			</div>

			<div class="flex flex-col gap-2" transition:fly={{ x: 100, duration: 350 }}>
				<label class="font-medium" for="location"> Location </label>
				<input
					class="shadow-md focus:outline-none focus:border-2 focus:border-violet-500 focus:shadow-sm focus:shadow-violet-300 py-2 px-3 w-72"
					name="location"
					bind:value={fields.location}
				/>
			</div>

			<div class="flex flex-col gap-2" transition:fly={{ x: 100, duration: 350 }}>
				<label class="font-medium" for="personalTwitter"> Personal Twitter </label>
				<input
					class="shadow-md focus:outline-none focus:border-2 focus:border-violet-500 focus:shadow-sm focus:shadow-violet-300 py-2 px-3 w-72"
					name="personalTwitter"
					bind:value={fields.personalTwitter}
				/>
			</div>

			<div class="flex flex-col gap-2" transition:fly={{ x: 100, duration: 350 }}>
				<label class="font-medium" for="personalTelegram"> Personal Telegram </label>
				<input
					class="shadow-md focus:outline-none focus:border-2 focus:border-violet-500 focus:shadow-sm focus:shadow-violet-300 py-2 px-3 w-72"
					name="personalTelegram"
					bind:value={fields.personalTelegram}
				/>
			</div>
		</div>

		<div class="social flex flex-col gap-3">
			<h1 class="text-2xl font-bold">Social Media</h1>

			{#if fields.twitter}
				<div class="flex flex-col gap-2" transition:fly={{ x: 100, duration: 350 }}>
					<label class="font-medium" for="twitter"> Twitter </label>
					<div class="flex">
						<input
							class="shadow-md bg-slate-50 text-slate-500 focus:outline-none focus:border-2 focus:border-sky-500 focus:shadow-sm focus:shadow-sky-300 py-2 px-3 w-72"
							name="twitter"
              readonly
							bind:value={fields.twitter}
						/>
						<button
							class="px-4 ml-2 self-center h-10 leading-4 justify-center transition-all bg-rose-600 shadow-md hover:bg-rose-700 hover:shadow-sm rounded-md text-md text-neutral-50 font-semibold"
							on:click={() => {
								fields.twitter = '';
							}}
						>
							X
						</button>
					</div>
				</div>
			{/if}

			{#if fields.linkedin}
				<div class="flex flex-col gap-2" transition:fly={{ x: 100, duration: 350 }}>
					<label class="font-medium" for="linkedin"> LinkedIn </label>
					<div class="flex">
						<input
							class="shadow-md bg-slate-50 text-slate-500 focus:outline-none focus:border-2 focus:border-sky-800 focus:shadow-sm focus:shadow-sky-600 py-2 px-3 w-72"
							name="linkedin"
              readonly
							bind:value={fields.linkedin}
						/>
						<button
							class="px-4 ml-2 self-center h-10 leading-4 justify-center transition-all bg-rose-600 shadow-md hover:bg-rose-700 hover:shadow-sm rounded-md text-md text-neutral-50 font-semibold"
							on:click={() => {
								fields.linkedin = '';
							}}
						>
							X
						</button>
					</div>
				</div>
			{/if}

			{#if fields.telegram}
				<div class="flex flex-col gap-2" transition:fly={{ x: 100, duration: 350 }}>
					<label class="font-medium" for="telegram"> Telegram </label>
					<div class="flex">
						<input
							class="shadow-md bg-slate-50 text-slate-500 focus:outline-none focus:border-2 focus:border-blue-600 focus:shadow-sm focus:shadow-blue-400 py-2 px-3 w-72"
              readonly
							bind:value={fields.telegram}
						/>
						<button
							class="px-4 ml-2 self-center h-10 leading-4 justify-center transition-all bg-rose-600 shadow-md hover:bg-rose-700 hover:shadow-sm rounded-md text-md text-neutral-50 font-semibold"
							on:click={() => {
								fields.telegram = '';
							}}
						>
							X
						</button>
					</div>
				</div>
			{/if}

			{#if fields.link}
				<div class="flex flex-col gap-2" transition:fly={{ x: 100, duration: 350 }}>
					<label class="font-medium" for="link"> Link </label>
					<div class="flex">
						<input
							class="shadow-md bg-slate-50 text-slate-500 focus:outline-none focus:border-2 focus:border-slate-500 focus:shadow-sm focus:shadow-slate-300 py-2 px-3 w-72"
							name="link"
              readonly
							bind:value={fields.link}
						/>
						<button
							class="px-4 ml-2 self-center h-10 leading-4 justify-center transition-all bg-rose-600 shadow-md hover:bg-rose-700 hover:shadow-sm rounded-md text-md text-neutral-50 font-semibold"
							on:click={() => {
								fields.link = '';
							}}
						>
							X
						</button>
					</div>
				</div>
			{/if}
		</div>
	</div>

	<div class="flex m-auto mt-4 justify-center border-2 border-neutral-400 p-4" style="width: 500px;">
		<div bind:this={signatureElement}>
			<Signature {...fields} />
		</div>
	</div>

	<div class="flex justify-center">
		<button
			class="text-white bg-violet-500 w-64 hover:transition-all hover:bg-violet-700 p-2 my-4 rounded-md shadow-md hover:shadow-sm"
			on:click={copySignature}
		>
			{buttonText}
		</button>
	</div>
</div>
