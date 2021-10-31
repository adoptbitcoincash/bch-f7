<Page name="account">
  <Navbar backLink="Back">
    <NavTitle sliding>{nonFungibleTokenVariation.name}</NavTitle>
    <NavRight>
      <Link popoverOpen=".popover-menu"><Icon f7="ellipsis_circle" color="black" /></Link>
    </NavRight>
  </Navbar>

  <NonFungibleTokenVariationMedia nonFungibleTokenVariation={nonFungibleTokenVariation} DB={DB}/>
  <NonFungibleTokenVariationAssets nonFungibleTokenVariation={nonFungibleTokenVariation} DB={DB} accounts={accounts}/>
  <NonFungibleTokenVariationInformations nonFungibleTokenVariation={nonFungibleTokenVariation} DB={DB}/>
</Page>

<script lang="ts">
  import { Page, Navbar, NavTitle, NavRight, Link, Icon } from 'framework7-svelte';
  import type { Accounts, NonFungibleTokenVariation } from "@adoptbitcoincash/bch-orm";
  import NonFungibleTokenVariationMedia from '../NonFungibleTokens/NonFungibleTokenVariationMedia.svelte';
  import NonFungibleTokenVariationInformations from '../NonFungibleTokens/NonFungibleTokenVariationInformations.svelte';
  import NonFungibleTokenVariationAssets from '../NonFungibleTokens/NonFungibleTokenVariationAssets.svelte';

  export let DB;
  export let accounts : Accounts;
  export let nonFungibleTokenVariation : NonFungibleTokenVariation;
</script>