<Card>
  <CardContent padding={false}>
    <List medial-list>
      <ListItem link={`/accounts/${account.id}/coins/${coin.id}/fungibleTokens/${fungibleToken.id}`} footer="{balance}" title={fungibleToken.name} after={fiat}>
        <img slot="media" alt="" src={BCH.cdn.getImage(`/cdn/tokens/small/${fungibleToken.id}.png`)} width="44"/>
      </ListItem>
    </List>
  </CardContent>
</Card>

<style>
</style>

<script lang="ts">
  import { Card, CardContent, List, ListItem } from 'framework7-svelte';
  import type { Account, Coin, FungibleToken, FungibleTokenBalance } from "@adoptbitcoincash/bch-orm";

  export let BCH;
  export let account : Account;
  export let coin : Coin;
  export let fungibleToken : FungibleToken;
  export let fungibleTokenBalance : FungibleTokenBalance;

  let balance = fungibleTokenBalance ? fungibleTokenBalance.toString() : `0 ${fungibleToken.id}`;
  let fiat = fungibleTokenBalance ? fungibleTokenBalance.toFiat(coin.usd) : `$ 0`;
</script>