<script context="module">
  export async function load({ params, fetch }) {
    const res = await fetch(`https://jsonplaceholder.typicode.com/posts/${params.id}`);

    const post = await res.json();

    return {
      props: {
        post
      }
    };
  };
</script>

<script>
	export let post;
</script>

<div class="container">
	<h1>{post.title}</h1>
	<p>{post.body}</p>
</div>

<style>
	.container {
		max-width: 900px;
		margin: 50px auto;
	}
</style>
