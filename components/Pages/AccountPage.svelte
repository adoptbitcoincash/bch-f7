<Page name="account" pageContent={false} withSubnavbar>
  <Navbar title={account.name} backLink="Back">
    {#if application && application.useNfts}
    <Subnavbar>
      <Segmented strong>
        <Button tabLink="#account-coins" tabLinkActive={tabActive === 'account-coins'}>Coins</Button>

        <Button tabLink="#account-assets" tabLinkActive={tabActive === 'account-assets'}>Assets</Button>
      </Segmented>
    </Subnavbar>
    {/if}
  </Navbar>

  <Tabs>
    <Tab id="account-coins" class="page-content" tabActive={tabActive === 'account-coins'} onTabShow={() => tabActive = 'account-coins'}>
      {#each coins as coin}
        <CoinBalance BCH={BCH} account={account} coin={coin} coinBalance={account.coinBalances.findByCoinId(coin.id).first()}/>
      {/each}
    </Tab>

    {#if application && application.useNfts}
    <Tab id="account-assets" class="page-content" tabActive={tabActive === 'account-assets'} onTabShow={() => tabActive = 'account-assets'}>
      <div class="nfts">
        {#each variationsIds as nftVariationId}
          <NftVariationVignette BCH={BCH} account={account} nftVariation={getVariation(nftVariationId)}/>
        {/each}
      </div>
    </Tab>
    {/if}

  </Tabs>
</Page>

<style>
  .nfts {display:flex; flex-wrap:wrap; margin:5px;}
</style>

<script lang="ts">
  import { Page, Navbar, Subnavbar, Segmented, Button, Tabs, Tab } from 'framework7-svelte';
  import CoinBalance from '../Fts/CoinBalance.svelte';
  import NftVariationVignette from '../Nfts/NftVariationVignette.svelte';
  import type { Account } from "@adoptbitcoincash/bch-orm";

  export let BCH;
  export let account : Account;

  let coins = BCH.hub.coins.findByIds(account.enabledCoinsIds).toArray();
  let variationsIds = account.nfts.getVariationsIds();
  let application = BCH.hub.applications.find(account.applicationId);
  let tabActive = application && application.useNfts ? 'account-assets' : 'account-coins';

  function getVariation(id: string) {
    return BCH.hub.nftVariations.find(id);
  }
</script>