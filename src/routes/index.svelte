<script context="module">
	export function preload() {
		return this.fetch(`blog.json`)
			.then((r) => r.json())
			.then((posts) => {
				return { posts };
			});
	}
</script>

<script>
	import Post from "../components/Post.svelte";

	export let posts;
</script>

<style>
	.Posts {
		display: grid;
		justify-content: space-between;
		grid-gap: 15px;
		grid-template-columns: 1fr;
	}
</style>

<svelte:head>
	<title>Matthew Rosell Felix</title>
	<meta name="description" content="Blog de matthewdrf live" />

	<meta name="twitter:card" content="summary_large_image" />
	<meta name="twitter:site" content="@matthewdrf" />
	<meta name="twitter:creator" content="@matthewdrf" />
	<meta name="twitter:title" content="Matthew Rosell" />
	<meta name="twitter:descripcion" content="Blog de matthewdrf live" />
	<meta
		name="twitter:image"
		content="https://arepa.s3.amazonaws.com/blogpost-cover.png" />

	<meta name="og:title" content="Matthew Rosell" />
	<meta name="og:description" content="Blog de matthewdrf live" />
	<meta
		name="og:image"
		content="https://arepa.s3.amazonaws.com/blogpost-cover.png" />
	<meta name="og:url" content="https://blog.matthewdrf.live" />
	<meta name="og:site_name" content="Matthew Rosell" />
	<meta name="og:locale" content="es_ES" />
	<meta name="og:type" content="article" />
	<meta name="fb:app_id" content="" />
</svelte:head>

<div class="Home">
	<div class="Posts">
		{#each posts as post}
			<Post {post} />
		{/each}
	</div>
</div>
