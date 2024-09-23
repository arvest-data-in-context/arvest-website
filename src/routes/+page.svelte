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
    <BigButton
        label = {PageVocab.start_creating[langVal]}
        url = {"/"}
    />

    <img id="main_demo_image" src="/imgs/network_visualization_hi_res.png" alt="arvest screen shot">
</div>

<div id="feature_section">
    <FeatureCard
        title = {PageVocab.features.create_collections.title[langVal]}
        description = {PageVocab.features.create_collections.desc[langVal]}
        image_url = "/imgs/create_collections.png"
        image_alt = "create collections image",
        button_label = {PageVocab.features.create_collections.button[langVal]}
    />
    <FeatureCard
        title = {PageVocab.features.create_annotations.title[langVal]}
        description = {PageVocab.features.create_annotations.desc[langVal]}
        image_url = "/imgs/create_collections.png"
        image_alt = "create collections image"
        button_label = {PageVocab.features.create_annotations.button[langVal]}
    />
    <FeatureCard
        title = {PageVocab.features.navigate_networks.title[langVal]}
        description = {PageVocab.features.navigate_networks.desc[langVal]}
        image_url = "/imgs/network_visualization_hi_res.png"
        image_alt = "create collections image"
        button_label = {PageVocab.features.navigate_networks.button[langVal]}
    />
    <FeatureCard
        title = {PageVocab.features.ml_workflows.title[langVal]}
        description = {PageVocab.features.ml_workflows.desc[langVal]}
        image_url = "/imgs/network_visualization_hi_res.png"
        image_alt = "create collections image"
        button_label = {PageVocab.features.ml_workflows.button[langVal]}
    />
    <FeatureCard
        title = {PageVocab.features.iiif_compliant.title[langVal]}
        description = {PageVocab.features.iiif_compliant.desc[langVal]}
        image_url = "/imgs/gallica.png"
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
</style>