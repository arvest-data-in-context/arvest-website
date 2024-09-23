<script>
	import './reset.css';
	import './theme.css';
	import { onMount } from 'svelte';

	import TopNav from '$lib/components/top_nav/TopNav.svelte';
	import Footer from '$lib/components/footer/Footer.svelte';

	let global_container;
	let scrolled = false;

	function handle_scroll(){
		scrolled = global_container.scrollTop > 0;
	};

	onMount(()=> {
		handle_scroll();
		global_container.addEventListener('scroll', function(e) {
			handle_scroll();
		})
	})
</script>


<div id="global_container" bind:this={global_container}>
	<div id="page_container" >
		<TopNav 
			scrolled = {scrolled}
		/>

		<div id="content_container">
			<slot />
		</div>

		
	</div>

	<Footer />
</div>

<style>
	#global_container{
		width: 100%;
		height: 100%;
		background: linear-gradient(to bottom, var(--background-color-1) 70%, var(--background-color-2));
		position: fixed;
		z-index: -1;
		top: 0;
    	left: 0;
		overflow: auto;
	}

	#page_container{
		position: relative;
	}

	#content_container{
		padding-left: 10em;
		padding-right: 10em;
	}

	/* LARGE SCREENS */
    @media (min-width: 1500px) {
        #content_container{
            padding-left: 10em;
			padding-right: 10em;
        }
    }

    /* MEDIUM SCREENS */
    @media (min-width: 1200px) and (max-width: 1499px)  {
        #content_container{
            padding-left: 5em;
			padding-right: 5em;
        }
    }

    /* SMALL SCREENS */
    @media (min-width: 700px) and (max-width: 1199px) {
        #content_container{
            padding-left: 2em;
			padding-right: 2em;
        }
    }

    /* VERY SMALL SCREENS */
    @media (max-width: 699px) {
        #content_container{
            padding-left: 1em;
			padding-right: 1em;
        }
    }
</style>