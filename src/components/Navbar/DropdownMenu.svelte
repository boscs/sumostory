<script>
    import "./navbar.css";
	import { beforeUpdate } from 'svelte';
    export let open;
	beforeUpdate(() => {
		console.log('the component is about to update', open);
	});
</script>
			
<style>	
	
</style>

<div class="dropdown" class:open={open}>
    <slot></slot>
</div>