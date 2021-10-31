<Block>
  <BlockTitle>{$_('my.nfts')}</BlockTitle>
  <NonFungibleTokenVariationAssetsList DB={DB} accounts={accounts} nonFungibleTokenVariation={nonFungibleTokenVariation} />
</Block>

<style></style>

<script lang="ts">
  import { _ } from 'svelte-i18n';
  import { BlockTitle, Block } from 'framework7-svelte';
  import type { Accounts, NonFungibleTokenVariation } from "@adoptbitcoincash/bch-orm";
  import NonFungibleTokenVariationAssetsList from './NonFungibleTokenVariationAssetsList.svelte';

  export let DB;
  export let accounts : Accounts;
  export let nonFungibleTokenVariation : NonFungibleTokenVariation;
</script>