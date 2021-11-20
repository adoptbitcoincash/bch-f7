<BlockTitle>Informations</BlockTitle>
<List>
  <ListItem title="Name" after={nftCollection.name}/>
  <Social social={nftCollection.social}/>
</List>

<script lang="ts">
  import { BlockTitle, List, ListItem } from 'framework7-svelte';
  import Social from '../Social/Social.svelte';
  import type { NftCollection } from "@adoptbitcoincash/bch-orm"
  export let nftCollection : NftCollection;
</script>