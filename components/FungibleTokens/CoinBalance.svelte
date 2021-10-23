<Card>
  <CardContent padding={false}>
    <List medial-list>
      <ListItem link={`/accounts/${account.id}/coins/${coinBalance.id}`} footer="{coinBalance.toString()}" title={coin.name} after={fiat}>
        <img slot="media" alt="" src="/cdn/tokens/small/{coinBalance.id}.png" width="44"/>
      </ListItem>
    </List>
  </CardContent>
</Card>

<style>
</style>

<script lang="ts">
  import { Card, CardContent, List, ListItem } from 'framework7-svelte';

  export let DB;
  export let account;
  export let coinBalance;

  let coin = DB.hub.coins.find(coinBalance.coinId);
  let fiat = coinBalance.toFiat(coin.usd);
</script>