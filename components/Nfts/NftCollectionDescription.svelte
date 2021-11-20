{#if nftCollection.description}
  <Description description={nftCollection.getDescription()} />
{/if}

<script lang="ts">
  import type { NftCollection } from '@adoptbitcoincash/bch-orm';
  import Description from '../Various/Description.svelte';

  export let nftCollection : NftCollection;
</script>