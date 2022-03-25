<script context="module">
	import { Row, Col, Styles, Icon } from 'sveltestrap';
	import { onMount } from 'svelte';
</script>

<script lang="ts">
	let hue = [50];

	onMount(() => {
		console.log('onMount');
	});
</script>

<Styles />

<Row cols={{ lg: 12, md: 12, sm: 12 }}>
	<Col xs="1" style="text-align: right;">
		{#if hue[0] === 50}
			<Icon name="circle-fill" style="color: grey;" />
		{:else}
			<Icon name="check-circle-fill" style="color: green;" />
		{/if}
	</Col>
	<Col xs="11">
		<div class="range_box">
			<input
				type="range"
				class="range"
				bind:value={hue[0]}
				min="0"
				max="100"
				style="background: linear-gradient(to right, {hue[0] === 50
					? 'grey'
					: 'red'} 0%, {hue[0] === 50 ? 'grey' : 'red'} {hue[0]}%, {hue[0] === 50
					? 'grey'
					: '#fff'} {hue[0]}%, {hue[0] === 50 ? 'grey' : '#fff'} 100%); border:1px solid {hue[0] ===
				50
					? 'grey'
					: 'red'}"
			/>
		</div>
	</Col>
</Row>

<style>
	.range {
		-webkit-appearance: none;
		appearance: none;
		padding: 0;
		cursor: pointer;
		width: 100%;
		height: 7px;
		border-radius: 10px;
	}
	.range::-webkit-slider-thumb {
		-webkit-appearance: none;
		border: 2px solid red;
		background: #fff;
		height: 14px;
		width: 14px;
		border-radius: 50%;
	}
	.range_box {
		padding-right: 20px;
	}
</style>
