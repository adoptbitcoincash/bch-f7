<Page name="coin">
  <Navbar backLink="Back">
    <NavTitle sliding>{coin.name}</NavTitle>
    <NavRight>
      <Link popoverOpen=".popover-menu"><Icon f7="ellipsis_circle" color="black" /></Link>
    </NavRight>
  </Navbar>

  <div style="text-align:center; margin-top:20px; margin-bottom:20px; ">
    <img src={DB.cdn.getImage(`/cdn/tokens/large/${coin.id}.png`)} alt="" class="visual" style="width:100px; height:100px;"/>
    <div style="margin-top:10px; font-size:160%; font-weight:bold;">{fiat}</div>
    <div style="margin-top:5px; font-size:100%; color:#999;">{balance}</div>
  </div>

  <Block style="margin-top:0;">
    <Row>
      <Col>
        <Button raised fill round style="height:36px;"><Icon f7="arrow_up_circle_fill" size="24px" color="white" style="margin-right:5px;" /> Send</Button>
      </Col>
      <Col>
        <Button raised fill round style="height:36px;"><Icon f7="plus_circle_fill" size="24px" color="white" style="margin-right:5px;" /> Receive</Button>
      </Col>
    </Row>
  </Block>

  {#each fungibleTokens as fungibleToken}
    <FungibleTokenBalance DB={DB} account={account} coin={coin} fungibleToken={fungibleToken} fungibleTokenBalance={account.fungibleTokenBalances.findByFungibleTokenId(fungibleToken.id).first()}/>
  {/each}

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
  import { Page, Navbar, NavTitle, NavRight, Link, Icon, Popover, List, ListItem, Block, Row, Col, Button } from 'framework7-svelte';
  import FungibleTokenBalance from '../FungibleTokens/FungibleTokenBalance.svelte';
  import type { Account, Coin } from "@adoptbitcoincash/bch-orm";

  export let DB;
  export let account : Account;
  export let coin : Coin;

  let coinBalance = account.coinBalances.findByCoinId(coin.id).first();
  let fungibleTokens = DB.hub.fungibleTokens.findByCoinId(coin.id).toArray();

  let balance = coinBalance ? coinBalance.toString() : `0 ${coin.id}`;
  let fiat = coinBalance ? coinBalance.toFiat(coin.usd) : `$ 0`;

/*
  import PopupMove from '../components/PopupMove.svelte';
  import PopupSend from '../components/PopupSend.svelte';
*/
</script>