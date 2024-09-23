<script>
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();

    let revealed = false

    function handle_reveal(){
        if(revealed == false){
            revealed = true;
        }
        else{
            revealed = false;
        }

        dispatch('update_hamburger', {
			state: revealed
		});
    }
</script>

<div>
    <button on:click={handle_reveal}>
        <img src="/imgs/ui/hamburger.png" alt="hambuerger menu logo">
    </button>
</div>

<style>
    button{
        border: none;
        background-color: transparent;
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center; 
    }

    img{
        height: 40px;
        margin: auto;
    }

    button:hover{
        background-color: grey;
        border-radius: 20px;
    }
</style>