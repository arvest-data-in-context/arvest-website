<script>
    import SiteLogo from '$lib/components/top_nav/SiteLogo.svelte';
    import TopNavLink from '$lib/components/top_nav/TopNavLink.svelte';
    import BigButton from '$lib/components/general_ui/BigButton.svelte';
    import LangSelect from '$lib/components/top_nav/LangSelect.svelte';

    export let scrolled = false;

    // Language handling:
    import { lang } from '$lib/scripts/stores.js';
    import PageVocab from '$lib/data/vocab/top_nav.json';
    let langVal;
	lang.subscribe(value => {
		langVal = value;
	});
</script>

<header class="{scrolled ? 'with-border' : 'no-border'}">
    <nav>
        <SiteLogo />

        <ul>
            <TopNavLink 
                label = {PageVocab.community[langVal]}
                url = {"/"}
            />
            <TopNavLink 
                label = {PageVocab.learn[langVal]}
                url = {"/"}
            />
            <TopNavLink 
                label = {PageVocab.api[langVal]}
                url = {"/"}
            />
            <TopNavLink 
                label = {PageVocab.about[langVal]}
                url = {"/"}
            />
        </ul>
    </nav>
</header>

<div class="top_right_content">
    <LangSelect />
    <BigButton
        label = {PageVocab.connect[langVal]}
        url = {"/"}
    />
</div>

<div id="nav_padding"></div>

<style>
    header{
        width: 100%;
        padding-left: 12em;
        padding-right: 12em;
        padding-top: 0.7em;
        padding-bottom: 0.7em;
        background-color: var(--background-color-1);
        position: fixed;
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
        position: fixed;
        top:0;
        right:0;
        align-items: center;
        display: flex;
        gap: 0.5em;
        flex-wrap: wrap;
        padding-right: 10em;
        padding-top: 0.75em;
    }

    .with-border{
        border-bottom: solid grey 1px;
    }

    .no-border{
        border-bottom: none;
    }

    #nav_padding{
        height: 100px;
    }

    /* LARGE SCREENS */
    @media (min-width: 1500px) {
        header{
            padding-left: 12em;
            padding-right: 12em;
        }
        .top_right_content{
            padding-right: 10em;
        }
    }

    /* MEDIUM SCREENS */
    @media (min-width: 1200px) and (max-width: 1499px)  {
        header{
            padding-left: 6em;
            padding-right: 6em;
        }
        .top_right_content{
            padding-right: 5em;
        }
    }

    /* SMALL SCREENS */
    @media (min-width: 700px) and (max-width: 1199px) {
        header{
            padding-left: 2em;
            padding-right: 2em;
        }
        .top_right_content{
            padding-right: 2em;
        }
    }

    /* VERY SMALL SCREENS */
    @media (max-width: 699px) {
        header{
            padding-left: 1em;
            padding-right: 1em;
        }
        .top_right_content{
            padding-right: 0.9em;
        }
    }
</style>