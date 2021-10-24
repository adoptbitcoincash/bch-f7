<Page name="token">
  <Navbar title={fungibleToken.name} backLink="Back" />

  <div style="text-align:center; margin-top:20px; margin-bottom:20px; ">
    <img src="/cdn/tokens/large/{fungibleToken.id}.png" alt="" class="visual" style="width:100px; height:100px;"/>
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
  
  <BlockTitle>Transaction history</BlockTitle>
  <List noChevron>
    {#each transactions as transaction}
      {#if transaction.identityId}
        <ListItem link="#" header={transaction.date} title={transaction.title} footer={transaction.amount} after={transaction.fiat}>
          <img slot="media" class="message-avatar" src="https://cdn.framework7.io/placeholder/people-100x100-9.jpg" alt="" />
        </ListItem>
      {:else}
        <ListItem link="#" header={transaction.date} title={transaction.title} footer={transaction.amount} after={transaction.fiat}>
          <i slot="media" class="f7-icons">person_alt_circle</i>
        </ListItem>
      {/if}
    {/each}
  </List>


</Page>

<script lang="ts">
  import { Page, Navbar, Block, Row, Col, Button, Icon, List, ListItem, BlockTitle } from 'framework7-svelte';
  import type { Account, Coin, FungibleToken } from "@adoptbitcoincash/bch-orm";

  export let DB;
  export let account : Account;
  export let coin : Coin;
  export let fungibleToken : FungibleToken;

  let fungibleTokenBalance = account.fungibleTokenBalances.findByFungibleTokenId(fungibleToken.id).first();
  let balance = fungibleTokenBalance ? fungibleTokenBalance.toString() : `0 ${fungibleToken.id}`;
  let fiat = fungibleTokenBalance ? fungibleTokenBalance.toFiat(coin.usd) : `$ 0`;

  let transactions = [
    {date: "24 oct", title: "Unknow", amount:"0.03945203 BCH", fiat:"$ -10.34"},
    {date: "22 oct", title: "Florence Consul", amount:"4.29485923 BCH", fiat:"$ 2304.34", identityId: 'florence'}
  ]
</script>