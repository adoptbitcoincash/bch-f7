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
      {#each account.coinBalances.toArray() as coinBalance}
        <CoinBalance DB={DB} account={account} coinBalance={coinBalance}/>
      {/each}
    </Tab>

    <Tab id="account-assets" class="page-content" tabActive={tabActive === 'account-assets'} onTabShow={() => tabActive = 'account-assets'}>
      <div class="nfts">
        {#each account.nonFungibleTokens.toArray() as nonFungibleToken}
          <NonFungibleTokenVignette DB={DB} account={account} nonFungibleToken={nonFungibleToken}/>
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
  import NonFungibleTokenVignette from '../NonFungibleTokens/NonFungibleTokenVignette.svelte';
//  import NonFungibleTokenVignette from './NonFungibleTokenVignette.svelte';
  import type { Account } from "@adoptbitcoincash/bch-orm";

  export let DB;
  export let account : Account;

  let tabActive = 'account-coins';
</script>