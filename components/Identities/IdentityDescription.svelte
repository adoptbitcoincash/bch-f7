{#if identity.description}
  <Description description={identity.getDescription()} />
{/if}

<script lang="ts">
  import type { Identity } from '@adoptbitcoincash/bch-orm';
  import Description from '../Various/Description.svelte';

  export let identity : Identity;
</script>