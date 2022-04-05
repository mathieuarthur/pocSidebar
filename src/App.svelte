<script>
	import { fade } from 'svelte/transition';
	let visible = true;

	function toggleVisible()
	{
		visible = !visible
	}
</script>
<div class="container">
		{#if visible}
			<div on:mouseover={toggleVisible} on:focus={()=>null} class="Test" transition:fade> 
				<div class="burger">
					<div></div>
					<div></div>
					<div></div>
				</div>
			</div>
		{/if}

		<div class={`sidebar ${visible ? "hidden" : ""}`} on:mouseout={toggleVisible} on:blur={()=>null}> 
			<ul>
				<li>tes</li>
				<li>dsqdqs</li>
				<li>dsqdqs</li>
				<li>fgsdgfd</li>
			</ul>
		</div>
	</div>

<style>
	.container
	{
		position: fixed;
		display: flex;
		align-items: center;
		height: 100%;
		width: 100%;
	}
	.burger
	{	
		margin-left: 5px;
		width: fit-content;
		height: fit-content;
		border: solid 1px black;
		background-color: red;
	}
	.burger div
	{
		display: block;
		background-color: black;
		width: 	2em;
		height: 0.3em;
		margin: 5px;
	}
	ul
	{
		list-style: none;
		margin: 0;
		padding: 0;
	}
	.sidebar
	{
		background-color: green;
		position: absolute;
		left: 0px;
		transition: all 1s;
	}
	.sidebar.hidden
	{
		transition: all 1s;
		left: -100px;
	}
</style>