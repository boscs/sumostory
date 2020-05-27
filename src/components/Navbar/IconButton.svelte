<script>
	import "./navbar.css";
	export let href;
    export let icon;
	export let open = false;
	export let hasSubMenu;
	href = href || '#';
	hasSubMenu = hasSubMenu || false;
	const clickHandler = (ev)=>{
		ev.preventDefault();
		if(href === "#" && !hasSubMenu){
			open=!open;
			return false;
		} 
		return true;
	}
</script>

<style>
</style>

<li class="nav-item">
    <a {href} class="icon-button" on:click={clickHandler}>
        <slot name="icon">{icon}</slot>
    </a>
	{#if open}
   		<slot></slot>
	{/if}
</li>

