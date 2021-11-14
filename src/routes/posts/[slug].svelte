<script context="module">
  export async function load({ page }) {
    try {


    const Post = await import(`../../posts/${page.params.slug}.md`)
    return {
      props: {
        Post: Post.default,
      }
    }
  } catch (e) {
    // Redirect example
    // return {
    //   status:303,
    //   redirect: "/posts"
    // }

    return {
      status: 404,
      error: `Post not found`
    }
  }
  }
</script>

<script>
  export let Post
</script>

<Post />

