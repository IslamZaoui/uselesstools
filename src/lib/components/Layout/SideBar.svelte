<script lang="ts">
	import { page } from '$app/stores';
</script>

<nav class="bg-surface-800 h-full w-[150px]">
	<div class=" flex flex-col gap-2 p-3 items-center">
		<a
			class="btn {$page.data.url === '/' ? 'variant-filled-primary' : 'variant-ringed-primary'} rounded w-full"
			href="/">صفحة الرئيسية</a
		>
		<a
			class="btn {$page.data.url === '/WeatherAI'
				? 'variant-filled-primary'
				: 'variant-ringed-primary'} rounded w-full"
			href="/WeatherAI">حالة الطقس</a
		>
	</div>
</nav>
