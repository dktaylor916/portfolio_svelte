<script>
  import favicon from "$lib/assets/favicon.svg";
  import Portfolio from "$lib/Portfolio.svelte";
  export const prerender = true;

  let { children } = $props();
</script>

<Portfolio />
