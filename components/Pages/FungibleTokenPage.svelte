<Page name="token">
  <Navbar title="Fungible Token" backLink="Back" />
</Page>

<script lang="ts">
  import { Page, Navbar } from 'framework7-svelte';
  import type { Account, Coin, FungibleToken } from "@adoptbitcoincash/bch-orm";

  export let DB;
  export let account : Account;
  export let coin : Coin;
  export let fungibleToken : FungibleToken;
</script>