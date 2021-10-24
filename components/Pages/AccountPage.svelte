<Page name="account" pageContent={false} withSubnavbar>
  <Navbar title={account.name} backLink="Back">
    <Subnavbar>
      <Segmented strong>
        <Button tabLink="#account-coins" tabLinkActive={tabActive === 'account-coins'}>Coins</Button>
        <Button tabLink="#account-assets" tabLinkActive={tabActive === 'account-assets'}>Assets</Button>
      </Segmented>
    </Subnavbar>
  </Navbar>

  <Tabs>
    <Tab id="account-coins" class="page-content" tabActive={tabActive === 'account-coins'} onTabShow={() => tabActive = 'account-coins'}>
      {#each coins as coin}
        <CoinBalance DB={DB} account={account} coin={coin} coinBalance={account.coinBalances.findByCoinId(coin.id).first()}/>
      {/each}
    </Tab>

    <Tab id="account-assets" class="page-content" tabActive={tabActive === 'account-assets'} onTabShow={() => tabActive = 'account-assets'}>
      <div class="nfts">
        {#each variationsIds as nonFungibleTokenVariationId}
          <NonFungibleTokenVariationVignette DB={DB} account={account} nonFungibleTokenVariation={getVariation(nonFungibleTokenVariationId)}/>
        {/each}
      </div>
    </Tab>

  </Tabs>
</Page>

<style>
  .nfts {display:flex; flex-wrap:wrap; margin:5px;}
</style>

<script lang="ts">
  import { Page, Navbar, Subnavbar, Segmented, Button, Tabs, Tab } from 'framework7-svelte';
  import CoinBalance from '../FungibleTokens/CoinBalance.svelte';
  import NonFungibleTokenVariationVignette from '../NonFungibleTokens/NonFungibleTokenVariationVignette.svelte';
  import type { Account } from "@adoptbitcoincash/bch-orm";

  export let DB;
  export let account : Account;

  let tabActive = 'account-coins';
  let coins = DB.hub.coins.toArray();
  let variationsIds = account.nonFungibleTokens.getVariationsIds();

  function getVariation(id: string) {
    return DB.hub.nonFungibleTokenVariations.find(id);
  }
</script>