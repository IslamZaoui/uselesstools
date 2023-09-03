<script lang="ts">
	import { page } from '$app/stores';
</script>

<nav class="bg-surface-800 h-full w-[150px]">
	<div class=" flex flex-col gap-2 p-3 items-center">
		<a
			class="btn variant-{$page.data.url === '/' ? 'filled' : 'ghost'}-primary rounded w-full"
			href="/">صفحة الرئيسية</a
		>
		<a
			class="btn variant-{$page.data.url === '/WeatherAI'
				? 'filled'
				: 'ghost'}-primary rounded w-full"
			href="/WeatherAI">حالة الطقس</a
		>
	</div>
</nav>
