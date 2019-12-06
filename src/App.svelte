<script>
	import Header from './Header.svelte';
	import Login from './Login.svelte';

	var isLogOpen = false;
	function loginOpen() {
		isLogOpen = true;
	}
	function loginClose() {
		isLogOpen = false;
	}
</script>

<Header on:loginOpen={loginOpen}/>
{#if isLogOpen}
	<Login on:loginClose={loginClose}/>
{/if}