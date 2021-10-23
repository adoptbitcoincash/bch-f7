<Page name="coin">
  <Navbar backLink="Back">
    <NavTitle sliding>{coin.name}</NavTitle>
    <NavRight>
      <Link popoverOpen=".popover-menu"><Icon f7="ellipsis_circle" color="black" /></Link>
    </NavRight>
  </Navbar>

  {#await fungibleTokenBalancePromise then fungibleTokenBalances}
    {#each fungibleTokenBalances as fungibleTokenBalance}
      <FungibleTokenBalance DB={DB} account={account} coin={coin} fungibleTokenBalance={fungibleTokenBalance}/>
    {/each}
  {/await}

  <Popover class="popover-menu">
    <List>
      <ListItem link="#" popoverClose popupOpen=".popup-move" title="Move" />
      <ListItem link="#" popoverClose popupOpen=".popup-send" title="Send" />
    </List>
  </Popover>
<!--
  <PopupMove/>
  <PopupSend/>
-->
</Page>

<script lang="ts">
  import { Page, Navbar, NavTitle, NavRight, Link, Icon, Popover, List, ListItem } from 'framework7-svelte';
  import FungibleTokenBalance from '../FungibleTokens/FungibleTokenBalance.svelte';
  import type { Account, Coin } from "@adoptbitcoincash/bch-orm";

  export let DB;
  export let account : Account;
  export let coin : Coin;

  let fungibleTokenBalancePromise = getFungibleTokenBalance();

  async function getFungibleTokenBalance() {
    let fungibleTokenBalances = await account.getFungibleTokenBalances();
    return fungibleTokenBalances.findByFungibleTokensIds(coin.fungibleTokensIds).toArray();
  }

/*
  import PopupMove from '../components/PopupMove.svelte';
  import PopupSend from '../components/PopupSend.svelte';
*/
</script>