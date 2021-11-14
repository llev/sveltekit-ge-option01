<script context="module">
  export async function load() {
    const posts = import.meta.globEager('../../posts/*.md');
    const postsList = Object.values(posts)
    const postsMeta = postsList.map((post) => {
      return post.metadata
    })
    return {
      props: {
        posts: postsMeta
      }
    };
  }
</script>

<script>
  export let posts
</script>


<div class="container m-0-auto">
  <slot />
  <aside>
    <h4>Archive</h4>
    <ui>
      {#each posts as post}
        <li><a sveltekit:prefetch href={`/posts/${post.slug}`}>{post.title}</a></li>
      {/each}
    </ui>
    
  </aside>
</div>