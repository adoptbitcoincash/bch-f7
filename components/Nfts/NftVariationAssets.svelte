<Block>
  <BlockTitle>{$_('my.nfts')}</BlockTitle>
  <NftVariationAssetsList BCH={BCH} accounts={accounts} nftVariation={nftVariation} />
</Block>

<style></style>

<script lang="ts">
  import { _ } from 'svelte-i18n';
  import { BlockTitle, Block } from 'framework7-svelte';
  import type { Accounts, NftVariation } from "@adoptbitcoincash/bch-orm";
  import NftVariationAssetsList from './NftVariationAssetsList.svelte';

  export let BCH;
  export let accounts : Accounts;
  export let nftVariation : NftVariation;
</script>