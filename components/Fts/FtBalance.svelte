<Card>
  <CardContent padding={false}>
    <List medial-list>
      <ListItem link={`/accounts/${account.id}/coins/${coin.id}/fts/${ft.id}`} footer="{balance}" title={ft.name} after={fiat}>
        <img slot="media" alt="" src={BCH.cdn.getImage(`/cdn/tokens/small/${ft.id}.png`)} width="44"/>
      </ListItem>
    </List>
  </CardContent>
</Card>

<style>
</style>

<script lang="ts">
  import { Card, CardContent, List, ListItem } from 'framework7-svelte';
  import type { Account, Coin, Ft, FtBalance } from "@adoptbitcoincash/bch-orm";

  export let BCH;
  export let account : Account;
  export let coin : Coin;
  export let ft : Ft;
  export let ftBalance : FtBalance;

  let balance = ftBalance ? ftBalance.toString() : `0 ${ft.id}`;
  let fiat = ftBalance ? ftBalance.toFiat(coin.usd) : `$ 0`;
</script>