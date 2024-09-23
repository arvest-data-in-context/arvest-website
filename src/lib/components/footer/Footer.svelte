<script>
    // Language handling:
    import { lang } from '$lib/scripts/stores.js';
    import PageVocab from '$lib/data/vocab/footer.json';
    let langVal;
	lang.subscribe(value => {
		langVal = value;
	});
</script>

<footer>
    <nav>
        <h2>{PageVocab.menu[langVal]}</h2>
        

        <div id="menus">
            <ul class="menu_section">
                <li><a href="/" class="menu_top_link">{PageVocab.community[langVal]}</a></li>
                <li><a href="/" class="menu_lower_link">{PageVocab.projects[langVal]}</a></li>
                <li><a href="/" class="menu_lower_link">{PageVocab.forum[langVal]}</a></li>
                <li><a href="/" class="menu_lower_link">{PageVocab.news[langVal]}</a></li>
                <li><a href="/" class="menu_lower_link">{PageVocab.stage[langVal]}</a></li>
            </ul>
    
            <ul class="menu_section">
                <li><a href="/" class="menu_top_link">{PageVocab.learn[langVal]}</a></li>
                <li><a href="/" class="menu_lower_link">{PageVocab.tutorials[langVal]}</a></li>
                <li><a href="/" class="menu_lower_link">{PageVocab.ml[langVal]}</a></li>
                <li><a href="/" class="menu_lower_link">{PageVocab.iiif[langVal]}</a></li>
                <li><a href="/" class="menu_lower_link">{PageVocab.other_tools[langVal]}</a></li>
            </ul>
    
            <ul class="menu_section">
                <li><a href="/" class="menu_top_link">{PageVocab.api[langVal]}</a></li>
                <li><a href="/" class="menu_lower_link">{PageVocab.reference[langVal]}</a></li>
            </ul>
    
            <ul class="menu_section">
                <li><a href="/" class="menu_top_link">{PageVocab.about[langVal]}</a></li>
                <li><a href="/" class="menu_lower_link">{PageVocab.about_arvest[langVal]}</a></li>
                <li><a href="/" class="menu_lower_link">{PageVocab.team[langVal]}</a></li>
                <li><a href="/" class="menu_lower_link">{PageVocab.accessibility[langVal]}</a></li>
                <li><a href="/" class="menu_lower_link">{PageVocab.credits[langVal]}</a></li>
            </ul>
    
            <ul class="menu_section">
                <li><a href="/" class="menu_top_link">{PageVocab.connect[langVal]}</a></li>
                <li><a href="/" class="menu_lower_link">{PageVocab.demo[langVal]}</a></li>
            </ul>
        </div>
        
    </nav>
</footer>

<style>
    footer{
        width: 100%;
        background-color: transparent;
        padding-top: 2em;
        padding-bottom: 2em;
        padding-left: 7em;
        padding-right: 7em;
    }

    #menus{
        display: grid;
        gap: 1em;
        grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
        font-size: 1em;
        width: 100%;
    }

    a{
        text-decoration: none;
        font-family: 'Input-Mono-Narrow-Thin', monospace;
    }

    .menu_section{
        width: 100%;
        font-size: 0.8em;
    }

    h2{
        padding-bottom: 1em;
        color: var(--primary-text);
        font-size: 1em;
    }

    .menu_top_link{
        color: var(--primary-text);
    }

    .menu_top_link:hover{
        text-decoration: underline;
    }

    .menu_lower_link{
        color: var(--secondary-text);
    }

    .menu_lower_link:hover{
        cursor: pointer;
        color: var(--primary-text);
    }

    li{
        padding-bottom: 0.3em;
    }

    /* LARGE SCREENS */
    @media (min-width: 1500px) {
        footer{
            padding-left: 14em;
            padding-right: 14em;
        }
        #menus{
            grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
        }
        .menu_section{
            font-size: 0.8em;
        }
        h2{
            font-size: 1em;
        }
    }

    /* MEDIUM SCREENS */
    @media (min-width: 1200px) and (max-width: 1499px)  {
        footer{
            padding-left: 7em;
            padding-right: 7em;
        }
        #menus{
            grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
        }
        .menu_section{
            font-size: 0.8em;
        }
        h2{
            font-size: 1em;
        }
    }

    /* SMALL SCREENS */
    @media (min-width: 700px) and (max-width: 1199px) {
        footer{
            padding-left: 3em;
            padding-right: 3em;
        }
        #menus{
            grid-template-columns: 1fr 1fr 1fr;
        }
        .menu_section{
            font-size: 0.7em;
        }
        h2{
            font-size: 0.8em;
        }
    }

    /* VERY SMALL SCREENS */
    @media (max-width: 699px) {
        footer{
            padding-left: 1em;
            padding-right: 1em;
        }
        #menus{
            grid-template-columns: 1fr 1fr;
        }
        .menu_section{
            font-size: 0.6em;
        }
        h2{
            font-size: 0.7em;
        }
    }
</style>