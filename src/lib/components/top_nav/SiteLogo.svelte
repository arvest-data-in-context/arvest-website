<script>
    export const img_src = "/arvest_logo_cut.png";
    export const alt_text = "arvest logo";
    export const site_name = "Arvest";
</script>

<div>
    <a href="/">
        <img src={img_src} alt="arvest logo">
        <p>{site_name}</p>
    </a>
</div>

<style>
    a{
        display: flex;
        text-decoration: none;
        color: var(--primary-text);
        height: 1.5em;
        align-content: center;
        align-items: center;
        gap: 0.5em;
        width: fit-content;
    }

    a:hover{
        cursor: pointer;
    }

    img{
        height: 100%;
    }

    p{
        font-size: 0.8em;
        align-self: center;
        font-family: 'Input-Mono-Narrow', monospace;
    }
</style>