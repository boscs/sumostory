<script>
	import "../components/NavBar/navbar.css";
	import IconButton from "../components/NavBar/IconButton.svelte";
	import DropdownItem from "../components/NavBar/DropdownItem.svelte";
	import DropdownMenu from "../components/NavBar/DropdownMenu.svelte";
	import Nav from '../components/Nav.svelte';
	import CustomNav from "../components/NavBar/CustomNav.svelte"
	export let segment;
	import {machines} from "./machines_list.js"
</script>
<style>
	main {
		position: relative;
		max-width: 56em;
		background-color: white;
		padding: 2em;
		margin: 0 auto;
		box-sizing: border-box;
	}
</style>

<CustomNav {segment}>
	<IconButton>
		<!-- Hamburger button -->
		<span slot="icon" class="material-icons">reorder</span>
		<DropdownMenu>
			<DropdownItem href="/" leftIcon="home" label="Accueil"/>
			<DropdownItem href="/startgame" leftIcon="games" label="Jeu découverte"/>
			<DropdownItem href="/QR_scan" leftIcon="camera_alt" label="Scanner une machine"/>
			<DropdownItem leftIcon="list" rightIcon='chevron_right' label="Inventaire des machines" >
				{#each machines as m}
					<DropdownItem href={`/machines/${m.name}` } leftIcon={m.leftIcon||""} label={m.name}/>
				{/each}
			</DropdownItem>
		</DropdownMenu>
	</IconButton>
</CustomNav>

<main>
	<slot></slot>
</main>