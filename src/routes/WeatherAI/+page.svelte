<script lang="ts">
	import { delay } from '$lib/utils';
	import { ProgressBar } from '@skeletonlabs/skeleton';

	let validate = false;

	let progressValue = 0;
	let comment = '';

	async function checkWeather() {
		const info = [
			'ارسال الموقع الى الخادم',
			'معالجة البيانات',
			'النظر خارج منزلك',
			'تجهيز بعض المعلومات الاضافية'
		];
		validate = true;
		for (let i = 0; i < 4; i++) {
			comment = info[i];
			for (let j = 0; j < 250; j++) {
				progressValue++;
				await delay(10);
			}
		}
	}
</script>

<div class="container h-full mx-auto p-4 flex justify-center items-center">
	<div class="flex flex-col items-center gap-2 w-full">
		{#if validate}
			<div class="w-[200px] text-center flex flex-col gap-3">
				{#await checkWeather()}
					<ProgressBar label="Progress Bar" max={1000} value={progressValue} />
					<span>{comment}</span>
				{:then x}
					<strong class='text-2xl'>مش عارف شوف وحدك</strong>
				{/await}
			</div>
		{:else}
			<h1 class="h1 text-2xl">اداة حالة الطقس</h1>
			<small>كشف حالة طقس بذكاء الاصطناعي</small>
			<form>
				<label class="label" dir="rtl">
					<span>ادخل ولايتك</span>
					<input class="input rounded" type="text" placeholder="مثلا: البليدة" />
					<button
						class="btn variant-ghost-secondary rounded hover:variant-filled-secondary"
						on:click={() => (validate = true)}>تحقق</button
					>
				</label>
			</form>
		{/if}
	</div>
</div>
