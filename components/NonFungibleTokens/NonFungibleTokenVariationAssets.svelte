<Block>
  <BlockTitle>{$_('my.nfts')}</BlockTitle>
  <NonFungibleTokenVariationAssetsList BCH={BCH} accounts={accounts} nonFungibleTokenVariation={nonFungibleTokenVariation} />
</Block>

<style></style>

<script lang="ts">
  import { _ } from 'svelte-i18n';
  import { BlockTitle, Block } from 'framework7-svelte';
  import type { Accounts, NonFungibleTokenVariation } from "@adoptbitcoincash/bch-orm";
  import NonFungibleTokenVariationAssetsList from './NonFungibleTokenVariationAssetsList.svelte';

  export let BCH;
  export let accounts : Accounts;
  export let nonFungibleTokenVariation : NonFungibleTokenVariation;
</script>