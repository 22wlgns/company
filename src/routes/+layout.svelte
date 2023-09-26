<script lang="ts">
    import './styles.css';
    import Sidebar from "$lib/components/sidebar/Sidebar.svelte";
    import { page } from '$app/stores';

    let showSidebar = false;

    $: path = $page.url.pathname;
    $: showSidebar = path !== '/';
</script>

<svelte:head>
    <title>iDEN.iT</title>
    <meta name="description" content="iDEN.iT Software"/>
</svelte:head>

{#if showSidebar}
    <Sidebar/>
{/if}

<div class="content {showSidebar ? 'content-with-sidebar' : ''}">
    <slot/>
</div>


<style>

</style>
