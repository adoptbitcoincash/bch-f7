<ListItem link={`/nfts/nftVariations/${nftVariation.id}/nfts/${nft.id}`} on:click={clicked}>
  <img slot="media" src={DB.cdn.getImage(nftVariation.image)} width="25" alt="" class="lazy" />
  <div slot="title">
    Mint {Math.floor(Math.random() * 150)} / 150
  </div>
</ListItem>

<style></style>

<script lang="ts">
  import { _ } from 'svelte-i18n';
  import { ListItem } from 'framework7-svelte';
  import type { NftVariation, Nft } from "@adoptbitcoincash/bch-orm";

  export let DB;
  export let nftVariation : NftVariation;
  export let nft : Nft;
  export let clicked;
</script>