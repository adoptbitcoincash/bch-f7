<List noChevron style="margin-left:10px;">
  {#each nonFungibleTokens.toArray() as nonFungibleToken}
    <NonFungibleTokenVariationAssetsListItem account={account} DB={DB} nonFungibleTokenVariation={nonFungibleTokenVariation} nonFungibleToken={nonFungibleToken} />
  {/each}
</List>

<style></style>

<script lang="ts">
  import { _ } from 'svelte-i18n';
  import { List } from 'framework7-svelte';
  import type { Account, NonFungibleTokenVariation, NonFungibleTokens } from "@adoptbitcoincash/bch-orm";
  import NonFungibleTokenVariationAssetsListItem from './NonFungibleTokenVariationAssetsListItem.svelte';

  export let DB;
  export let account : Account;
  export let nonFungibleTokenVariation : NonFungibleTokenVariation;
  export let nonFungibleTokens : NonFungibleTokens;
</script>