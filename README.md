**THIS HAS MIGRATED TO [GITLAB](https://gitlab.huma-num.fr/arvest/arvest.gitpages.huma-num.fr)***

# arvest.app

The website for the web app Arvest. This website was created using the [svelte](https://svelte.dev/) framework, for more info, consult their [docs](https://svelte.dev/docs/introduction).

## Domain and deployment

The website is deployed on [huma-num](https://www.huma-num.fr/)'s instanstance of gitlab, using [gitlab pages](https://docs.gitlab.com/ee/user/project/pages/).

The website is deployed at the domain `arvest.app` hosted at [INSERT DOMAIN HOST]().

## Adding and modifying content

To change the content of the website, push your changes to the main branch and the build will be taken care of automatically by gitlab. For a full guide on adding and modifying content, consult the docs [here](/docs/adding-content.md).

## Development

During devleopment, you can run a hot-reload server. Once you have cloned the repo, cd to the repo path and run:

```bash
npm run dev
```