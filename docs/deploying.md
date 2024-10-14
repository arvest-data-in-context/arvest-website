# Deploying

The website uses [huma-num](https://www.huma-num.fr/)'s instanstance of gitlab, using [gitlab pages](https://docs.gitlab.com/ee/user/project/pages/) to deploy the website. This page will take you through the steps that are taken to allows for this.

## Static adapter

Install the static website builder using the following:

```bash
npm i @sveltejs/adapter-static
```

The [svelte.config.js](/svelte.config.js) file has been modified to incorporate a static website builder which is used on build.

## Paths

In order to direct to the website domain on a page, you must first import the `base` variable from `$app/paths` in the top `<script>` element of the page and refer to this. For example:

```html
<script>
    import { base } from '$app/paths';
</script>
```

Then, within the page you can refer to url's in the following way:

```html
<a href="{base}/">Link to homepage</a>
<a href="{base}/about">Link to about page</a> 
```