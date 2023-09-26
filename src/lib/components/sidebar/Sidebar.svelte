<script lang="ts">
    import Notice from "$lib/components/sidebar/Notice.svelte";
    import My from "$lib/components/sidebar/My.svelte";
    import Home from "$lib/components/sidebar/Home.svelte";

    let hover = {
        home: false,
        notice: false,
    };

    type hoverKey = "home" | "notice";

    const onHover = (key: hoverKey) => {
        hover[key] = true;
    }

    const offHover = (key: hoverKey) => {
        hover[key] = false;
    }
</script>

<div class="sidebar">
    <a href="/my">
        <My/>
    </a>

    <a href="/home"
       on:mouseover={() => onHover('home')}
       on:mouseout={() => offHover('home')}
       on:focus={() => onHover('home')}
       on:blur={() => offHover('home')}
    >
        <Home hovered="{hover.home}"/>
    </a>

    <a href="/notice"
       on:mouseover={() => onHover('notice')}
       on:mouseout={() => offHover('notice')}
       on:focus={() => onHover('notice')}
       on:blur={() => offHover('notice')}
    >
        <Notice hovered="{hover.notice}"/>
    </a>
</div>

<style>
    .sidebar {
        position: fixed;
        top: 0;
        left: 0;
        width: 56px;
        height: 100%;
        padding: 20px 0;
        display: flex;
        align-content: center;
        flex-direction: column;
        gap: 32px;
        background: var(--color-theme-2);
    }

    a {
        width: 100%;
        height: 32px;
        display: flex;
        align-content: center;
        justify-content: center;
        flex-wrap: wrap;
    }
</style>