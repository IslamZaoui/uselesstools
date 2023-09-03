<script lang="ts">
	import { AppBar, type DrawerSettings } from '@skeletonlabs/skeleton';
	import { getDrawerStore } from '@skeletonlabs/skeleton';

	const drawerStore = getDrawerStore();

	const drawerSettings: DrawerSettings = {
		width: 'w-fit',
	};
</script>

<AppBar>
	<svelte:fragment slot="lead">
		<div class="space-x-2">
			<button class="btn-icon md:hidden" on:click={() => drawerStore.open(drawerSettings)}
				><i class="fa-solid fa-bars fa-xl" /></button
			>
			<strong class="text-xl">UselessTools ☝️🤓</strong>
		</div>
	</svelte:fragment>
	<svelte:fragment slot="trail">
		<a
			class="btn-icon"
			href="https://github.com/IslamZaoui/uselesstools"
			target="_blank"
			rel="noreferrer"
		>
			<i class="fa-brands fa-github fa-xl" />
		</a>
	</svelte:fragment>
</AppBar>
