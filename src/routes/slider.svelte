<script context="module">
	import { browser, dev } from '$app/env';
	import { Row, Col, Styles, Container } from 'sveltestrap';
	import CustomSlide from './components/CustomSlide.svelte';

	// we don't need any JS on this page, though we'll load
	// it in dev so that we get hot module replacement...
	export const hydrate = dev;

	// ...but if the client-side router is already loaded
	// (i.e. we came here from elsewhere in the app), use it
	export const router = browser;

	// since there's no dynamic data here, we can prerender
	// it so that it gets served as a static asset in prod
	export const prerender = true;
</script>

<Styles />

<svelte:head>
	<title>Slider</title>
</svelte:head>

<Container fluid>
	<Row>
		<h1>Choose Your Communication Style</h1>
		<p>
			Adjust the sliders to help us to communicate to you in a manner that fits your communication
			style.
		</p>
	</Row>
	<Row>
		<div class="title">
			<p>I know best to make decision.</p>
			<p>I look others to make decision.</p>
		</div>
	</Row>
	<CustomSlide />
	<Row>
		<div class="title">
			<p>Give me the details.</p>
			<p>Give me the big picture.</p>
		</div>
	</Row>
	<CustomSlide />
	<Row>
		<div class="title">
			<p>I move away from what i don't want.</p>
			<p>I gravitate toward what I do want.</p>
		</div>
	</Row>
	<CustomSlide />
	<Row>
		<div class="title">
			<p>Let's do it. Make it happen.</p>
			<p>Study & think it through first.</p>
		</div>
	</Row>
	<CustomSlide />
	<Row>
		<div class="title">
			<p>Tell me choice & possibilities.</p>
			<p>Show me steps & methods.</p>
		</div>
	</Row>
	<CustomSlide />
	<Row>
		<div class="title">
			<p>Tell me about it. Let me hear it</p>
			<p>Show me. Let me see it</p>
		</div>
	</Row>
	<CustomSlide />
</Container>

<style>
	h1 {
		text-align: left;
	}
	.title {
		display: flex;
		align-items: center;
		justify-content: space-between;
		margin-top: 20px;
		font-size: 14px;
		width: 95%;
		margin-left: auto;
		margin-right: 0;
	}
	.title p {
		width: 120px;
		padding: 0;
		margin: 0;
		text-align: left;
		color: #000;
		line-height: 15px;
		font-weight: 700;
	}
	.title p:last-child {
		text-align: right;
	}
</style>
