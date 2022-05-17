<script context="module">
	export const prerender = true;
</script>

<script>
	import Counter from '$lib/Counter.svelte';
	import ProfilePic from './ProfilePic.svelte';
	let src="http://blog.cutupsmethod.com/wp-content/uploads/2014/03/1472847_10152006289791826_1956446610_n.jpg"
    let title = "Various projects"
	const updateTitle = () => {
		title = "something completely different"
	}
</script>

<svelte:head>
	<title>Projects</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<h1>
		Projects
	</h1>

    <h2>{title}</h2>
	<ProfilePic src={src}/>

	<h2>
		try editing <strong>src/routes/index.svelte</strong>
	</h2>

	<button on:click={updateTitle}>change title</button>
    <input type="text" bind:value="{title}">
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
	}

	h1 {
		width: 100%;
	}

	.welcome {
		position: relative;
		width: 100%;
		height: 0;
		padding: 0 0 calc(100% * 495 / 2048) 0;
	}

	.welcome img {
		position: absolute;
		width: 100%;
		height: 100%;
		top: 0;
		display: block;
	}
</style>
