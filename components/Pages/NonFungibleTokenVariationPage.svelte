<Page name="account">
  <Navbar backLink="Back">
    <NavTitle sliding>{nonFungibleTokenVariation.name}</NavTitle>
    <NavRight>
      <Link popoverOpen=".popover-menu"><Icon f7="ellipsis_circle" color="black" /></Link>
    </NavRight>
  </Navbar>

  <NonFungibleTokenVariationMedia nonFungibleTokenVariation={nonFungibleTokenVariation} BCH={BCH}/>
  <NonFungibleTokenVariationAssets nonFungibleTokenVariation={nonFungibleTokenVariation} BCH={BCH} accounts={accounts}/>
  <NonFungibleTokenVariationInformations nonFungibleTokenVariation={nonFungibleTokenVariation} BCH={BCH}/>
</Page>

<script lang="ts">
  import { Page, Navbar, NavTitle, NavRight, Link, Icon } from 'framework7-svelte';
  import type { Accounts, NonFungibleTokenVariation } from "@adoptbitcoincash/bch-orm";
  import NonFungibleTokenVariationMedia from '../NonFungibleTokens/NonFungibleTokenVariationMedia.svelte';
  import NonFungibleTokenVariationInformations from '../NonFungibleTokens/NonFungibleTokenVariationInformations.svelte';
  import NonFungibleTokenVariationAssets from '../NonFungibleTokens/NonFungibleTokenVariationAssets.svelte';

  export let BCH;
  export let accounts : Accounts;
  export let nonFungibleTokenVariation : NonFungibleTokenVariation;
</script>