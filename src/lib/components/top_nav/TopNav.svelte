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

<style>
    header{
        width: 100%;
        padding-left: 2em;
        padding-right: 2em;
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
        padding-right: 2em;
        padding-top: 0.75em;
    }

    .with-border{
        border-bottom: solid grey 1px;
    }

    .no-border{
        border-bottom: none;
    }
</style>