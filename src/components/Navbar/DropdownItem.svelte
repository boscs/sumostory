<script>
  import "./navbar.css";
  export let href;
  href = href || '#';
  export let leftIcon;
  export let label;
  export let rightIcon;
  export let hasSubMenu;
  export let open = false;
  hasSubMenu = hasSubMenu || false;
	const clickHandler = ()=>{
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

<a {href} class="menu-item">
    {#if leftIcon }
      <span class="icon-button material-icons">{leftIcon}</span>
    {/if}
    <slot name="content">{label}</slot>
    {#if rightIcon}
      <span class="icon-right material-icons">{rightIcon}</span>
    {/if}
</a>
{#if open}
   <slot></slot>
{/if}


   