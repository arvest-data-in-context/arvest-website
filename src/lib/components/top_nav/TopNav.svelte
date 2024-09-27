<script>
    import { onMount } from 'svelte';

    import SiteLogo from '$lib/components/top_nav/SiteLogo.svelte';
    import TopNavLink from '$lib/components/top_nav/TopNavLink.svelte';
    import BigButton from '$lib/components/general_ui/BigButton.svelte';
    import LangSelect from '$lib/components/top_nav/LangSelect.svelte';
    import HamburgerMenu from '$lib/components/top_nav/HamburgerMenu.svelte';

    let small_screen = false;
    let hamburger_revealed = false;
    let scrolled = false;
    let show_border = false;
    let hamburger_element;

    // Language handling:
    import { lang } from '$lib/scripts/stores.js';
    import PageVocab from '$lib/data/vocab/top_nav.json';
    let langVal;
	lang.subscribe(value => {
		langVal = value;
	});

    const updateScreenWidth = () => {
        if(window.innerWidth < 1200){
            if(small_screen == false){
                small_screen = true;
            }
        }
        else{
            if(small_screen == true){
                small_screen = false;
            }
            hamburger_element.set_hamburger_state(false);
        }
    };

    onMount(() => {
        updateScreenWidth();

        window.addEventListener('resize', () => {
            updateScreenWidth()
        });

        handle_border_show();
    });

    function handle_border_show(){
        if(hamburger_revealed == true){
            show_border = true;
        }
        else{
            if(scrolled == true){
                show_border = true;
            }
            else{
                show_border = false;
            }
        };
    }

    function hangle_hamburger_state_change(e){
        hamburger_revealed = e.detail.state;
        handle_border_show();
    };

    export const handle_scroll = (scroll_state) => {
        scrolled = scroll_state;
        handle_border_show();
    }
</script>

<header class:show_border={show_border}>
    <nav>
        <SiteLogo />

        {#if small_screen == false}
            <ul>
                <li>
                    <TopNavLink 
                        label = {PageVocab.community[langVal]}
                        url = {"/"}
                    />
                </li>
                <li>
                    <TopNavLink 
                        label = {PageVocab.learn[langVal]}
                        url = {"/"}
                    />
                </li>
                <li>
                    <TopNavLink 
                        label = {PageVocab.api[langVal]}
                        url = {"/"}
                    />
                </li>
                <li>
                    <TopNavLink 
                        label = {PageVocab.about[langVal]}
                        url = {"/"}
                    />
                </li>
            </ul>
        {/if}
    </nav>

    {#if hamburger_revealed}
        <div id="hamburger_menu">
            <ul>
                <li>
                    <TopNavLink 
                        label = {PageVocab.community[langVal]}
                        url = {"/"}
                    />
                </li>
                <li>
                    <TopNavLink 
                        label = {PageVocab.learn[langVal]}
                        url = {"/"}
                    />
                </li>
                <li>
                    <TopNavLink 
                        label = {PageVocab.api[langVal]}
                        url = {"/"}
                    />
                </li>
                <li>
                    <TopNavLink 
                        label = {PageVocab.about[langVal]}
                        url = {"/"}
                    />
                </li>
            </ul>

            <div class="right_ham_cont">
                <LangSelect />
            </div>
        </div>
    {/if}
</header>

<div class="top_right_content">
    {#if small_screen == false}
        <LangSelect />
    {/if}
    <div id="hams" class="{small_screen ? "unhide_hams" : "hide_hams"}">
        <HamburgerMenu 
            bind:this={hamburger_element}
            on:update_hamburger={hangle_hamburger_state_change}
        />
    </div>
    
    <BigButton
        label = {PageVocab.connect[langVal]}
        url = {"/"}
    />
</div>

<div id="nav_padding"></div>

<style>
    .hide_hams{
        display: none;
    }
    .unhide_hams{
        display: block;
    }

    header{
        width: 100%;
        padding-left: 12em;
        padding-right: 12em;
        padding-top: 0.7em;
        padding-bottom: 0.7em;
        background-color: var(--background-color-1);
        position: fixed;
    }

    .show_border{
        border-bottom: solid grey 1px;
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

    #nav_padding{
        height: 100px;
    }

    #hamburger_menu{
        width: 100%;
        margin-top: 1em;
        display: flex;
        justify-content: space-between;
    }

    #hamburger_menu ul{
        display: inline;
    }

    #hamburger_menu ul li{
        padding-bottom: 0.5em;
    }

    .right_ham_cont{
        margin-right: 3.7em;
        font-size: 1em;
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
        .right_ham_cont{
            margin-right: 3.7em;
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
        .right_ham_cont{
            margin-right: 3.7em;
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
        .right_ham_cont{
            margin-right: 3.7em;
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
        .right_ham_cont{
            margin-right: 1.8em;
        }
    }
</style>