<script>
    export let label = "Link";
    export let url = "/";
</script>

<a href={url}>
    {label}
</a>

<style>
    a{
        font-size: 0.8em;
        align-self: center;
        font-family: 'Input-Mono-Narrow-Thin', monospace;
        color: var(--secondary-text);
        text-decoration: none;
    }

    a:hover{
        color: var(--primary-text);
        cursor: pointer;
    }
</style>