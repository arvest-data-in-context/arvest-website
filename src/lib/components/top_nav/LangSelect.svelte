<script>
    // Get the language store:
    import { lang } from '$lib/scripts/stores.js';

    // Retrieve the language:
    let setLang;
	lang.subscribe(value => {
		setLang = value;
	});

    // Update the language:
    function updateLang(){
        lang.set(setLang);
    }
</script>

<!--Language update select element-->
<select bind:value={setLang} on:change={() => updateLang()}>
    <option value="en">English</option>
    <option value="fr">Français</option>
</select>

<style>
    select{
        font-family: 'Input-Mono-Narrow-Thin', monospace;
        font-size: 0.5em;
        border: none;
        background-color: transparent;
    }

    select:hover{
        cursor: pointer;
    }
</style>