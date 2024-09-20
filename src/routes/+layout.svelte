<script>
	import './reset.css';
	import './theme.css';

	import TopNav from '$lib/components/top_nav/TopNav.svelte';
</script>

<div id="global_container">
	<div id="page_container">
		<TopNav />
		<br>
		<slot />
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
</style>