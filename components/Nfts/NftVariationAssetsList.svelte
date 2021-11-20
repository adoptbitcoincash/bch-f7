<List noChevron style="margin-left:10px;">
  {#each nfts.toArray() as nft}
    <NftVariationAssetsListItem BCH={BCH} nftVariation={nftVariation} nft={nft} />
  {/each}
</List>

<style></style>

<script lang="ts">
  import { _ } from 'svelte-i18n';
  import { List } from 'framework7-svelte';
  import type { Accounts, NftVariation } from "@adoptbitcoincash/bch-orm";
  import NftVariationAssetsListItem from './NftVariationAssetsListItem.svelte';

  export let BCH;
  export let accounts : Accounts;
  export let nftVariation : NftVariation;
  let nfts = accounts.nfts.findByNftVariationId(nftVariation.id);
</script>