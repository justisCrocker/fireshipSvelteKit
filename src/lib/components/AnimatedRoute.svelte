<script>
  import { fly } from "svelte/transition";
  import { page } from "$app/stores";
</script>

<!-- key is used to rerender all children when something changes, in this case the page url-->
<!-- this way the animation will happen each time the url changes -->
{#key $page.url}
  <div in:fly={{ x: "-100%", duration: 500 }}>
    <slot />
  </div>
{/key}
