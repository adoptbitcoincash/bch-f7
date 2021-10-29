{#if nonFungibleTokenCollection.description}
  <Description description={nonFungibleTokenCollection.getDescription()} />
{/if}

<script lang="ts">
  import type { NonFungibleTokenCollection } from '@adoptbitcoincash/bch-orm';
  import Description from '../Various/Description.svelte';

  export let nonFungibleTokenCollection : NonFungibleTokenCollection;
</script>