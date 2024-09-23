<script>
	import './reset.css';
	import './theme.css';
	import { onMount } from 'svelte';

	import TopNav from '$lib/components/top_nav/TopNav.svelte';

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
</style>