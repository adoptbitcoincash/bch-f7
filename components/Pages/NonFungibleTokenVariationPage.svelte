<Page name="account">
  <Navbar backLink="Back">
    <NavTitle sliding>{nonFungibleTokenVariation.name}</NavTitle>
    <NavRight>
      <Link popoverOpen=".popover-menu"><Icon f7="ellipsis_circle" color="black" /></Link>
    </NavRight>
  </Navbar>

  <NonFungibleTokenVariationMedia nonFungibleTokenVariation={nonFungibleTokenVariation} DB={DB}/>
  <NonFungibleTokenVariationInformations nonFungibleTokenVariation={nonFungibleTokenVariation} DB={DB}/>
  <NonFungibleTokenVariationAssets nonFungibleTokenVariation={nonFungibleTokenVariation} nonFungibleTokens={nonFungibleTokens} DB={DB} account={account}/>
</Page>

<script lang="ts">
  import { Page, Navbar, NavTitle, NavRight, Link, Icon } from 'framework7-svelte';
  import type { Account, NonFungibleTokenVariation } from "@adoptbitcoincash/bch-orm";
  import NonFungibleTokenVariationMedia from '../NonFungibleTokens/NonFungibleTokenVariationMedia.svelte';
  import NonFungibleTokenVariationInformations from '../NonFungibleTokens/NonFungibleTokenVariationInformations.svelte';
  import NonFungibleTokenVariationAssets from '../NonFungibleTokens/NonFungibleTokenVariationAssets.svelte';

  export let DB;
  export let account : Account;
  export let nonFungibleTokenVariation : NonFungibleTokenVariation;
  let nonFungibleTokens = account.nonFungibleTokens.findByNonFungibleTokenVariationId(nonFungibleTokenVariation.id);
</script>