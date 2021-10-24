<Block>
  <BlockTitle>{$_('your.assets')}</BlockTitle>
  <NonFungibleTokenVariationAssetsList DB={DB} account={account} nonFungibleTokenVariation={nonFungibleTokenVariation} nonFungibleTokens={nonFungibleTokens} />
</Block>

<style></style>

<script lang="ts">
  import { _ } from 'svelte-i18n';
  import { BlockTitle, Block } from 'framework7-svelte';
  import type { Account, NonFungibleTokenVariation, NonFungibleTokens } from "@adoptbitcoincash/bch-orm";
  import NonFungibleTokenVariationAssetsList from './NonFungibleTokenVariationAssetsList.svelte';

  export let DB;
  export let account : Account;
  export let nonFungibleTokenVariation : NonFungibleTokenVariation;
  export let nonFungibleTokens : NonFungibleTokens;
</script>