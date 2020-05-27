<script>
	import "./navbar.css";
	export let segment;
	console.log(segment);
</script>
<style>

</style>
<nav class="navbar">
	<ul class="navbar-nav">
		<slot></slot>
	</ul>
</nav>