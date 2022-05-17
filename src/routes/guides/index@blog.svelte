<script context="module">
	export const prerender = true;
	export async function load({fetch}) {
		// fetch any data needed for this component
		const res = await fetch('https://jsonplaceholder.typicode.com/posts')
		const posts = await res.json()
		console.log(posts)
		if (res.ok) {
			console.log(posts)
			return {
				props: {
					posts
				}
			}
		}

		return {
			status: res.status,
			error: new Error('Could not fetch posts')
		}
	}
</script>

<script>
	import ProfilePic from '../ProfilePic.svelte';
    import Title from '$lib/title.svelte';
import { post } from '../todos';
    // import REGL from 'regl';
    // import Hydra from 'hydra-ts';
	let src="http://blog.cutupsmethod.com/wp-content/uploads/2014/03/1472847_10152006289791826_1956446610_n.jpg"
    let title = "Various projects"
	const updateTitle = () => {
		title = "something completely different"
	};
	export let posts;
</script>

<svelte:head>
	<title>Projects</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
    <Title title="GEOFFREY MADDOCK"/>
	<h1>
		Blogs
	</h1>

    <div class="posts">
		<ul>
			{#each posts as post}
				<li>
					<a href={`/guides/${post.id}`}>{ post.title }</a>
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
