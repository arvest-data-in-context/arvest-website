<script>
    import SiteLogo from '$lib/components/top_nav/SiteLogo.svelte';
    import TopNavLink from '$lib/components/top_nav/TopNavLink.svelte';
</script>

<header>
    <nav>
        <SiteLogo />

        <ul>
            <TopNavLink />
            <TopNavLink />
            <TopNavLink />
        </ul>
        
    </nav>
</header>

<style>
    header{
        width: 100%;
        padding-left: 1em;
        padding-right: 1em;
        padding-top: 0.5em;
        background-color: var(--background-color-1);
    }

    nav{
        width: 100%;
        display: flex;
        align-items: center;
        gap: 1em;
    }

    ul{
        display: flex;
        align-items: center;
        gap: 1em;
    }
</style>