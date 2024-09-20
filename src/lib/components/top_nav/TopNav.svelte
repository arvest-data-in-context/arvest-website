<script>
    import SiteLogo from '$lib/components/top_nav/SiteLogo.svelte';
    import TopNavLink from '$lib/components/top_nav/TopNavLink.svelte';
    import BigButton from '$lib/components/general_ui/BigButton.svelte';
</script>

<header>
    <nav>
        <SiteLogo />

        <ul>
            <TopNavLink />
            <TopNavLink />
            <TopNavLink />
        </ul>

        <div class="top_right_content">
            <BigButton />
        </div>
        
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

    .top_right_content{
        position: absolute;
        top:0;
        right:0;
        align-items: center;
        display: flex;
        gap: 0.5em;
        flex-wrap: wrap;
        padding-right: 0.5em;
        padding-top: 0.5em;
    }
</style>