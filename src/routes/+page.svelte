<script>
    import Logo from "$lib/components/index/Logo.svelte";
    import Slack from "$lib/components/index/Slack.svelte";
    import {onMount} from "svelte";

    let showSlack = false;

    onMount(() => {
        setTimeout(() => {
            showSlack = true;
        }, 1500);
    });
</script>

<div class="body">
    <div>
        <Logo/>
    </div>

    {#if showSlack}
        <div>
            <Slack/>
        </div>
    {/if}
</div>

<style>
    .body {
        width: 100%;
        height: 100%;
        background-attachment: fixed;
        background-color: var(--color-bg-1);
        background-size: 100vw 100vh;
        background-image: radial-gradient(
                50% 50% at 50% 50%,
                rgba(255, 255, 255, 0.75) 0%,
                rgba(255, 255, 255, 0) 100%
        ),
        linear-gradient(180deg, var(--color-bg-0) 0%, var(--color-bg-1) 15%, var(--color-bg-2) 50%);
    }

    .body div {
        display: flex;
        align-content: center;
        justify-content: center;
    }
</style>
