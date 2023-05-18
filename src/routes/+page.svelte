<script lang="ts">
	let fields = {
		name: 'Josh Gragg',
		title: 'Head of Design',
		number: '555-666-1337',
		location: 'Colorado Springs, CO (MDT)',
    personalTwitter: '',
    personalTelegram: '',

		twitter: 'https://twitter.com/TheBlock__',
		linkedin: 'https://linkedin.com/company/theblockcrypto/',
		telegram: 'https://t.me/theblock',
		link: 'https://www.theblock.co/',
    proLink: 'https://www.theblock.pro',
    proTwitter: 'https://www.twitter.com/TheBlockPro__'
	};

  const hoverable = {
    'twitter': false,
    'linkedin': false,
    'telegram': false,
    'link': false,
    proLink: false,
    proTwitter: false
  }

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

  function resetToDefaults() {
    fields =  {
      name: 'Josh Gragg',
      title: 'Head of Design',
      number: '555-666-1337',
      location: 'Colorado Springs, CO (MDT)',
      personalTwitter: '',
      personalTelegram: '',

      twitter: 'https://twitter.com/TheBlock__',
      linkedin: 'https://linkedin.com/company/theblockcrypto/',
      telegram: 'https://t.me/theblock',
      link: 'https://www.theblock.co/',
      proLink: 'https://www.theblock.pro',
      proTwitter: 'https://www.twitter.com/TheBlockPro__'
    }
  }

  function highlightBox (label: string, flag: boolean) {
    hoverable[label] = flag
  }
</script>

<div>
	<div class="flex gap-12 p-4 justify-center border-2 bg-slate-50 border-slate-50 shadow-md w-auto">
		<div class="personal flex items-end flex-col gap-4">
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
				<label class="flex gap-2 font-medium" for="number"> 
          Phone number
          <div class="capitalize p-1 rounded-md font-semibold text-xs bg-purple-200 text-purple-600">
            OPTIONAL
          </div>
        </label>
				<input
					class="shadow-md focus:outline-none focus:border-2 focus:border-violet-500 focus:shadow-sm focus:shadow-violet-300 py-2 px-3 w-72"
					name="number"
					bind:value={fields.number}
				/>
			</div>

			<div class="flex flex-col gap-2" transition:fly={{ x: 100, duration: 350 }}>
				<label class="flex gap-2 font-medium" for="location">
          Location 
          <div class="capitalize p-1 rounded-md font-semibold text-xs bg-purple-200 text-purple-600">
            OPTIONAL
          </div>
        </label>
				<input
					class="shadow-md focus:outline-none focus:border-2 focus:border-violet-500 focus:shadow-sm focus:shadow-violet-300 py-2 px-3 w-72"
					name="location"
					bind:value={fields.location}
				/>
			</div>

			<div class="flex flex-col gap-2" transition:fly={{ x: 100, duration: 350 }}>
				<label class="flex gap-2 font-medium" for="personalTwitter">
          Personal Twitter 
          <div class="capitalize p-1 rounded-md font-semibold text-xs bg-purple-200 text-purple-600">
            OPTIONAL
          </div>
        </label>
				<input
					class="shadow-md focus:outline-none focus:border-2 focus:border-sky-500 focus:shadow-sm focus:shadow-sky-300 py-2 px-3 w-72"
					name="personalTwitter"
					bind:value={fields.personalTwitter}
				/>
			</div>

			<div class="flex flex-col gap-2" transition:fly={{ x: 100, duration: 350 }}>
				<label class="flex gap-2 font-medium" for="personalTelegram">
          Personal Telegram 
          <div class="capitalize p-1 rounded-md font-semibold text-xs bg-purple-200 text-purple-600">
            OPTIONAL
          </div>
        </label>
				<input
					class="shadow-md focus:outline-none focus:border-2 focus:border-blue-800 focus:shadow-sm focus:shadow-blue-600 py-2 px-3 w-72"
					name="personalTelegram"
					bind:value={fields.personalTelegram}
				/>
			</div>
		</div>

		<div class="social flex flex-col gap-4">
			<h1 class="text-2xl font-bold">Social Media</h1>

			{#if fields.twitter}
				<div class="flex flex-col gap-2" transition:fly={{ x: 100, duration: 350 }}>
					<label class="font-medium" for="twitter"> Twitter </label>
					<div class="flex">
						<input
							class="shadow-md focus:outline-none focus:border-2 focus:border-sky-500 focus:shadow-sm focus:shadow-sky-300 py-2 px-3 w-72 transition-colors"
              class:bg-slate-50={!hoverable.twitter}
              class:text-slate-500={!hoverable.twitter}
              class:bg-rose-300={hoverable.twitter}
              class:text-rose-800={hoverable.twitter}
							name="twitter"
              disabled readonly
							bind:value={fields.twitter}
						/>
						<button
							class="px-4 ml-2 self-center h-10 leading-4 justify-center transition-all bg-rose-600 shadow-md hover:bg-rose-700 hover:shadow-sm rounded-md text-md text-neutral-50 font-semibold"
							on:click={() => {
								fields.twitter = '';
							}}
              on:mouseover={() => highlightBox('twitter', true)}
              on:mouseout={() => highlightBox('twitter', false)}
						>
							Hide
						</button>
					</div>
				</div>
			{/if}

			{#if fields.linkedin}
				<div class="flex flex-col gap-2" transition:fly={{ x: 100, duration: 350 }}>
					<label class="font-medium" for="linkedin"> LinkedIn </label>
					<div class="flex">
						<input
							class="shadow-md focus:outline-none focus:border-2 focus:border-sky-800 focus:shadow-sm focus:shadow-sky-600 py-2 px-3 w-72 transition-colors"
              class:bg-slate-50={!hoverable.linkedin}
              class:text-slate-500={!hoverable.linkedin}
              class:bg-rose-300={hoverable.linkedin}
              class:text-rose-800={hoverable.linkedin}
							name="linkedin"
              disabled readonly
							bind:value={fields.linkedin}
						/>
						<button
							class="px-4 ml-2 self-center h-10 leading-4 justify-center transition-all bg-rose-600 shadow-md hover:bg-rose-700 hover:shadow-sm rounded-md text-md text-neutral-50 font-semibold"
							on:click={() => {
								fields.linkedin = '';
							}}
              on:mouseover={() => highlightBox('linkedin', true)}
              on:mouseout={() => highlightBox('linkedin', false)}
						>
							Hide
						</button>
					</div>
				</div>
			{/if}

			{#if fields.telegram}
				<div class="flex flex-col gap-2" transition:fly={{ x: 100, duration: 350 }}>
					<label class="font-medium" for="telegram"> Telegram </label>
					<div class="flex">
						<input
							class="shadow-md focus:outline-none focus:border-2 focus:border-blue-600 focus:shadow-sm focus:shadow-blue-400 transition-colors py-2 px-3 w-72"
              class:bg-slate-50={!hoverable.telegram}
              class:text-slate-500={!hoverable.telegram}
              class:bg-rose-300={hoverable.telegram}
              class:text-rose-800={hoverable.telegram}
              disabled readonly
							bind:value={fields.telegram}
						/>
						<button
							class="px-4 ml-2 self-center h-10 leading-4 justify-center transition-all bg-rose-600 shadow-md hover:bg-rose-700 hover:shadow-sm rounded-md text-md text-neutral-50 font-semibold"
							on:click={() => {
								fields.telegram = '';
							}}
              on:mouseover={() => highlightBox('telegram', true)}
              on:mouseout={() => highlightBox('telegram', false)}
						>
							Hide
						</button>
					</div>
				</div>
			{/if}

			{#if fields.link}
				<div class="flex flex-col gap-2" transition:fly={{ x: 100, duration: 350 }}>
					<label class="font-medium" for="link"> Link </label>
					<div class="flex">
						<input
							class="shadow-md focus:outline-none focus:border-2 focus:border-slate-500 focus:shadow-sm focus:shadow-slate-300 py-2 px-3 w-72 transition-colors"
              class:bg-slate-50={!hoverable.link}
              class:text-slate-500={!hoverable.link}
              class:bg-rose-300={hoverable.link}
              class:text-rose-800={hoverable.link}
							name="link"
              disabled readonly
							bind:value={fields.link}
						/>
						<button
							class="px-4 ml-2 self-center h-10 leading-4 justify-center transition-all bg-rose-600 shadow-md hover:bg-rose-700 hover:shadow-sm rounded-md text-md text-neutral-50 font-semibold"
              on:mouseover={() => highlightBox('link', true)}
              on:mouseout={() => highlightBox('link', false)}
							on:click={() => {
								fields.link = '';
							}}
						>
							Hide
						</button>
					</div>
				</div>
			{/if}

			{#if fields.proLink}
				<div class="flex flex-col gap-2" transition:fly={{ x: 100, duration: 350 }}>
					<label class="flex gap-2 font-medium" for="link">
            Pro URL
          </label>
					<div class="flex">
						<input
							class="shadow-md focus:outline-none focus:border-2 focus:border-slate-500 focus:shadow-sm focus:shadow-slate-300 py-2 px-3 w-72 transition-colors"
              class:bg-slate-50={!hoverable.proLink}
              class:text-slate-500={!hoverable.proLink}
              class:bg-rose-300={hoverable.proLink}
              class:text-rose-800={hoverable.proLink}
							name="link"
              disabled readonly
							bind:value={fields.proLink}
						/>
						<button
							class="px-4 ml-2 self-center h-10 leading-4 justify-center transition-all bg-rose-600 shadow-md hover:bg-rose-700 hover:shadow-sm rounded-md text-md text-neutral-50 font-semibold"
              on:mouseover={() => highlightBox('proLink', true)}
              on:mouseout={() => highlightBox('proLink', false)}
							on:click={() => {
								fields.proLink = '';
							}}
						>
							Hide
						</button>
					</div>
				</div>
			{/if}

			{#if fields.proTwitter}
				<div class="flex flex-col gap-2" transition:fly={{ x: 100, duration: 350 }}>
					<label class="flex gap-2 font-medium" for="link">
            Pro Twitter
          </label>
					<div class="flex">
						<input
							class="shadow-md focus:outline-none focus:border-2 focus:border-slate-500 focus:shadow-sm focus:shadow-slate-300 py-2 px-3 w-72 transition-colors"
              class:bg-slate-50={!hoverable.proTwitter}
              class:text-slate-500={!hoverable.proTwitter}
              class:bg-rose-300={hoverable.proTwitter}
              class:text-rose-800={hoverable.proTwitter}
							name="link"
              disabled readonly
							bind:value={fields.proTwitter}
						/>
						<button
							class="px-4 ml-2 self-center h-10 leading-4 justify-center transition-all bg-rose-600 shadow-md hover:bg-rose-700 hover:shadow-sm rounded-md text-md text-neutral-50 font-semibold"
              on:mouseover={() => highlightBox('proTwitter', true)}
              on:mouseout={() => highlightBox('proTwitter', false)}
							on:click={() => {
								fields.proTwitter = '';
							}}
						>
							Hide
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

	<div class="flex flex-col items-center justify-center">
		<button
			class="text-white bg-violet-500 w-64 hover:transition-all hover:bg-violet-700 p-2 my-4 rounded-md shadow-md hover:shadow-sm active:scale-x-90 transition-transform"
			on:click={copySignature}
		>
			{buttonText}
		</button>
		<button
			class="text-white bg-violet-600 w-64 hover:transition-all hover:bg-violet-700 p-2 my-4 rounded-md shadow-md hover:shadow-sm active:scale-x-90 transition-transform"
			on:click={resetToDefaults}
		>
			Reset to Defaults
		</button>
	</div>
</div>
