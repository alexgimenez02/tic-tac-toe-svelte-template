<script lang="ts">
	import { SvelteMap } from "svelte/reactivity";
	
	const board = new SvelteMap();

	function handleClick() {}
	
</script>

<svelte:head>
	<title>Noughts and Crosses</title>
</svelte:head>
<div class="game"> 
	<h1 class="title">Noughts and Crosses</h1>
	<p class="subtitle">Player X turn</p>

	<div class="board">
		{#each Array(9), i}
		<!-- svelte-ignore a11y_click_events_have_key_events -->
		<!-- svelte-ignore a11y_interactive_supports_focus -->
		<div class="cell"
			role="button"
			onclick={handleClick}
			>
			{board.get(i)}
		</div>
		{/each}
	</div>

	<button class="button">
		<p>Reset</p>
	</button>
</div>

<style>
@import './styles.css';
</style>