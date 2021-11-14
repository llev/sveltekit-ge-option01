<script context="module">
  export function load({ error, status }) {
    return {
      props: {
        error,
        status
      }
    }
  }
</script>

<script>
  export let status
  export let error
</script>
<main class="container">
<h1 class="text-4xl">Boooooooooooooooooooooooooooooooooooooooöooooooooooooooooooooooooooooooooooooooo</h1>
<h2>{status}</h2>
<h3>{error.message}</h3>
</main>

