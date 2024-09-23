<script>
    import BigButton from '$lib/components/general_ui/BigButton.svelte';

    export let title = "Title";
    export let description = "Description";
    export let image_url = "/favicon.png";
    export let image_alt = "image";
    export let button_label = "Button";
    export let button_url = "/";
</script>

<div id="container">
    <div id="text_content">
        <h2>
            {title}
        </h2>
        <p id="desc">
            {description}
        </p>

        <div style="font-size: 0.7em;">
        <BigButton
            label = {button_label}
            url = {button_url}
        />
        </div>
    </div>
    <img src={image_url} alt={image_alt}>
</div>

<style>
    #container{
        padding-top: 3em;
        padding-bottom: 3em;
        width: 100%;
        display: flex;
        gap: 1em;
    }

    #text_content{
        width: 30%;
        height: fit-content;
    }

    h2{
        color: var(--primary-text);
        font-size: 0.7em;
        padding-bottom: 0.2em;
        width: 100%;
    }

    #desc{
        color: var(--secondary-text);
        font-size: 0.5em;
        padding-bottom: 1em;
    }

    img{
        width: 70%;
    }
</style>