<Page name="account">
  <Navbar backLink="Back">
    <NavTitle sliding>{nftVariation.name}</NavTitle>
    <NavRight>
      <Link popoverOpen=".popover-menu"><Icon f7="ellipsis_circle" color="black" /></Link>
    </NavRight>
  </Navbar>

  <NftVariationMedia nftVariation={nftVariation} BCH={BCH}/>
  <NftVariationAssets nftVariation={nftVariation} BCH={BCH} accounts={accounts}/>
  <NftVariationInformations nftVariation={nftVariation} BCH={BCH}/>
</Page>

<script lang="ts">
  import { Page, Navbar, NavTitle, NavRight, Link, Icon } from 'framework7-svelte';
  import type { Accounts, NftVariation } from "@adoptbitcoincash/bch-orm";
  import NftVariationMedia from '../Nfts/NftVariationMedia.svelte';
  import NftVariationInformations from '../Nfts/NftVariationInformations.svelte';
  import NftVariationAssets from '../Nfts/NftVariationAssets.svelte';

  export let BCH;
  export let accounts : Accounts;
  export let nftVariation : NftVariation;
</script>