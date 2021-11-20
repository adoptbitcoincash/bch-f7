<Card>
  <CardContent padding={false}>
    <List medial-list>
      <ListItem link={`/accounts/${account.id}/coins/${coin.id}`} footer={balance} title={coin.name} after={fiat}>
        <img slot="media" alt="" src={BCH.cdn.getImage(`/cdn/tokens/small/${coin.id}.png`)} width="44"/>
      </ListItem>
    </List>
  </CardContent>
</Card>

<style>
</style>

<script lang="ts">
  import { Card, CardContent, List, ListItem } from 'framework7-svelte';
  import type { Account, Coin, CoinBalance } from "@adoptbitcoincash/bch-orm";

  export let BCH;
  export let account : Account;
  export let coin : Coin;
  export let coinBalance : CoinBalance | null = null;

  let balance = coinBalance ? coinBalance.toString() : `0 ${coin.id}`;
  let fiat = coinBalance ? coinBalance.toFiat(coin.usd) : `$ 0`;
</script>