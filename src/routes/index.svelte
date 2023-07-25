<script context="module">
  export async function load({fetch}) {
    try {
      const res = await fetch('/blog/all.json')
      const data = await res.json()
      return {
        props: data
      }
    } catch (err) {
      console.log('500:', err)
    }
  }
</script>

<script>
  import AuthorCard from '$lib/AuthorCard.svelte'
  import PostsGrid from '$lib/PostsGrid.svelte'

  export let posts
</script>

<svelte:head>
  <title>Wassink.io</title>
</svelte:head>

<h1>Whats going on?</h1>

<PostsGrid {posts} />

<a href="/second">Page 2</a>

