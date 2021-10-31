<ListItem link={`/nonFungibleTokens/nonFungibleTokenVariations/${nonFungibleTokenVariation.id}/nonFungibleTokens/${nonFungibleToken.id}`} on:click={clicked}>
  <img slot="media" src={nonFungibleTokenVariation.image.cdn} width="25" alt="" />
  <div slot="title">
    Mint {Math.floor(Math.random() * 150)} / 150
  </div>
</ListItem>

<style></style>

<script lang="ts">
  import { _ } from 'svelte-i18n';
  import { ListItem } from 'framework7-svelte';
  import type { NonFungibleTokenVariation, NonFungibleToken } from "@adoptbitcoincash/bch-orm";

  export let DB;
  export let nonFungibleTokenVariation : NonFungibleTokenVariation;
  export let nonFungibleToken : NonFungibleToken;
  export let clicked;
</script>