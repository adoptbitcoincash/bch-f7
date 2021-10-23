<Card>
  <CardContent padding={false}>
    <List medial-list>
      <ListItem link={`/accounts/${account.id}/coins/${coin.id}/fungibletokens/${fungibleTokenBalance.id}`} footer="{fungibleTokenBalance.toString()}" title={fungibleToken.name} after={fiat}>
        <img slot="media" alt="" src="/cdn/tokens/small/{fungibleToken.id}.png" width="44"/>
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
  export let coin;
  export let fungibleTokenBalance;

  let fungibleToken = DB.hub.fungibleTokens.find(fungibleTokenBalance.fungibleTokenId);
  fungibleTokenBalance.fungibleToken = fungibleToken;
  let fiat = fungibleTokenBalance.toFiat(coin.usd);
</script>