<script>
    import BigButton from '$lib/components/general_ui/BigButton.svelte';
    import FeatureCard from '$lib/components/front_page/FeatureCard.svelte';

    // Language handling:
    import { lang } from '$lib/scripts/stores.js';
    import PageVocab from '$lib/data/vocab/front_page.json';
    let langVal;
	lang.subscribe(value => {
		langVal = value;
	});
</script>



<div id="top_section">
    <h1>
        {PageVocab.short_description[langVal]}
    </h1>
    <p id="long_description">
        {PageVocab.long_description[langVal]}
    </p>
    <div id="main_button_resizer">
    <BigButton
        label = {PageVocab.start_creating[langVal]}
        url = {"/"}
    />
    </div>

    

    <img id="main_demo_image" src="/imgs/front_page_content/network_visualization_hi_res.png" alt="arvest screen shot">
</div>

<div id="feature_section">
    <FeatureCard
        title = {PageVocab.features.create_collections.title[langVal]}
        description = {PageVocab.features.create_collections.desc[langVal]}
        image_url = "/imgs/front_page_content/create_collections.png"
        image_alt = "create collections image"
        button_label = {PageVocab.features.create_collections.button[langVal]}
    />
    <FeatureCard
        title = {PageVocab.features.create_annotations.title[langVal]}
        description = {PageVocab.features.create_annotations.desc[langVal]}
        image_url = "/imgs/front_page_content/create_collections.png"
        image_alt = "create collections image"
        button_label = {PageVocab.features.create_annotations.button[langVal]}
    />
    <FeatureCard
        title = {PageVocab.features.navigate_networks.title[langVal]}
        description = {PageVocab.features.navigate_networks.desc[langVal]}
        image_url = "/imgs/front_page_content/network_visualization_hi_res.png"
        image_alt = "create collections image"
        button_label = {PageVocab.features.navigate_networks.button[langVal]}
    />
    <FeatureCard
        title = {PageVocab.features.ml_workflows.title[langVal]}
        description = {PageVocab.features.ml_workflows.desc[langVal]}
        image_url = "/imgs/front_page_content/network_visualization_hi_res.png"
        image_alt = "create collections image"
        button_label = {PageVocab.features.ml_workflows.button[langVal]}
    />
    <FeatureCard
        title = {PageVocab.features.iiif_compliant.title[langVal]}
        description = {PageVocab.features.iiif_compliant.desc[langVal]}
        image_url = "/imgs/front_page_content/gallica.png"
        image_alt = "create collections image"
        button_label = {PageVocab.features.iiif_compliant.button[langVal]}
    />
</div>

<style>
    h1{
        color: var(--primary-text);
        font-size: 2em;
        padding-bottom: 0.2em;
        width: 60%;
    }

    #long_description{
        color: var(--secondary-text);
        padding-bottom: 1em;
    }

    #top_section{
        padding-top: 3em;
        padding-bottom: 3em;
        gap: 1em;
        width: 80%;
    }

    #main_demo_image{
        margin-top: 2em;
        width: 100%;
        border-radius: 5px;
    }

    #main_button_resizer{
        font-size: 1em;
    }

    /* LARGE SCREENS */
    @media (min-width: 1500px) {
        h1{
            font-size: 2em;
        }
        #long_description{
            font-size: 1em;
        }
        #main_button_resizer{
            font-size: 1em;
        }
        #top_section{
            padding-top: 3em;
        }
    }

    /* MEDIUM SCREENS */
    @media (min-width: 1200px) and (max-width: 1499px)  {
        h1{
            font-size: 2em;
        }
        #long_description{
            font-size: 1em;
        }
        #main_button_resizer{
            font-size: 1em;
        }
        #top_section{
            padding-top: 1em;
        }
    }

    /* SMALL SCREENS */
    @media (min-width: 700px) and (max-width: 1199px) {
        h1{
            font-size: 2em;
        }
        #long_description{
            font-size: 0.7em;
        }
        #main_button_resizer{
            font-size: 1em;
        }
        #top_section{
            padding-top: 2em;
        }
    }

    /* VERY SMALL SCREENS */
    @media (max-width: 699px) {
        h1{
            font-size: 1em;
        }
        #long_description{
            font-size: 0.5em;
        }
        #main_button_resizer{
            font-size: 0.7em;
        }
        #top_section{
            padding-top: 3em;
        }
    }
</style>