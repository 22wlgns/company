<script lang="ts">
	import { fly } from 'svelte/transition';
	import { onMount } from 'svelte';

	let visible = false;

	onMount(() => (visible = true));
</script>

{#if visible}
	<img
		src="/images/logo.svg"
		alt="iDEN.iT Logo"
		draggable="false"
		in:fly={{ y: 100, duration: 1500 }}
	/>
{:else}
	<div style="height: 16rem" />
{/if}

<style>
	img {
		height: 32rem;
		width: 32rem;
		user-select: none;
	}
</style>
