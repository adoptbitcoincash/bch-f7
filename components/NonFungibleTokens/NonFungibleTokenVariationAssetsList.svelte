<List noChevron style="margin-left:10px;">
  {#each nonFungibleTokens.toArray() as nonFungibleToken}
    <NonFungibleTokenVariationAssetsListItem BCH={BCH} nonFungibleTokenVariation={nonFungibleTokenVariation} nonFungibleToken={nonFungibleToken} />
  {/each}
</List>

<style></style>

<script lang="ts">
  import { _ } from 'svelte-i18n';
  import { List } from 'framework7-svelte';
  import type { Accounts, NonFungibleTokenVariation } from "@adoptbitcoincash/bch-orm";
  import NonFungibleTokenVariationAssetsListItem from './NonFungibleTokenVariationAssetsListItem.svelte';

  export let BCH;
  export let accounts : Accounts;
  export let nonFungibleTokenVariation : NonFungibleTokenVariation;
  let nonFungibleTokens = accounts.nonFungibleTokens.findByNonFungibleTokenVariationId(nonFungibleTokenVariation.id);
</script>