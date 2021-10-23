<div class="nft">
  <div class="visual2">
    <div class="visual"><Link href={`/accounts/${account.id}/nonfungibletokens/${nonFungibleToken.id}/`}><img src="{nonFungibleToken.variation.image.cdn}" alt=""/></Link></div>
  </div>
</div>

<style>
  .nft {flex: 46%; margin: 2%; margin-bottom:20px; max-height:200px;}
  .visual2 {height:200px;}
  .visual {  display: flex; justify-content: center; align-items: center; height:200px;}
  .visual img {max-width: 100%; max-height:200px;}
  .infos {text-align:left; padding-top:5px;}
  .infos .name {font-size: .875rem; font-weight:700; line-height: 1.4; letter-spacing: -.011em;}
  .infos .more {font-size: .75rem; font-weight:600; color:#374047; letter-spacing:-.011em;}
</style>


<script lang="ts">
  import { Link } from 'framework7-svelte';
  import type { Account, NonFungibleToken } from "@adoptbitcoincash/bch-orm";

  export let DB;
  export let account : Account;
  export let nonFungibleToken : NonFungibleToken;
</script>