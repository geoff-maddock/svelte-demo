<script context="module">
	export const prerender = true;
	export async function load({fetch}) {
		// fetch any data needed for this component
		const res = await fetch('https://dev.arcane.city/api/events?filters[name]=cutups&limit=10000')
		const events = await res.json()
		console.log(events)
		if (res.ok) {
			console.log(events)
			return {
				props: {
					events
				}
			}
		}

		return {
			status: res.status,
			error: new Error('Could not fetch events')
		}
	}
</script>

<script>
	import ProfilePic from '../ProfilePic.svelte';
    import Title from '$lib/title.svelte';
	let src="http://blog.cutupsmethod.com/wp-content/uploads/2014/03/1472847_10152006289791826_1956446610_n.jpg"
    let title = "Various projects"
	const updateTitle = () => {
		title = "something completely different"
	};
	export let events
</script>

<svelte:head>
	<title>Projects</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
    <Title title="GEOFFREY MADDOCK"/>
	<h1>
		CAT
	</h1>

    <div class="events">
		<ul>
			{#each events["data"] as event}
				<li>
					<a href="https://dev.arcane.city/events/{event.slug}">{event.name}</a>
				</li>
			{/each}
		</ul>
	</div>

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
