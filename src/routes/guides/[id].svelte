<script context="module">
	export const prerender = true;
	export async function load({fetch, params}) {
		// fetch any data needed for this component
        const id = params.id;
		const res = await fetch(`https://jsonplaceholder.typicode.com/posts/${id}`)
		const post = await res.json()
        console.log(id)
		console.log(post)
		if (res.ok) {
			console.log(post)
			return {
				props: {
					post
				}
			}
		}

		return {
			status: 301,
            redirect: '/guides'
			// error: new Error('Could not fetch the post')
		}
	}
</script>

<script>
	import ProfilePic from '../ProfilePic.svelte';
    import Title from '$lib/title.svelte';
    // import REGL from 'regl';
    // import Hydra from 'hydra-ts';
	let src="http://blog.cutupsmethod.com/wp-content/uploads/2014/03/1472847_10152006289791826_1956446610_n.jpg"
    let title = "Various projects"
	const updateTitle = () => {
		title = "something completely different"
	};
	export let post;
</script>

<svelte:head>
	<title>Projects</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
    <Title title="GEOFFREY MADDOCK"/>
	<h1>
		Post
	</h1>

    <div class="posts">
		<h2>{post.title}</h2>
        <p>{post.body}</p>
		
	</div>

</section>

<style>
    .posts {
        margin-top: 40px;
        padding: 10px;

    }
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
