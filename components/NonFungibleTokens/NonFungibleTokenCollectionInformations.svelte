<BlockTitle>Informations</BlockTitle>
<List>
  <ListItem title="Name" after={nonFungibleTokenCollection.name}/>
  <Social social={nonFungibleTokenCollection.social}/>
</List>

<script lang="ts">
  import { BlockTitle, List, ListItem } from 'framework7-svelte';
  import Social from '../Social/Social.svelte';
  import type { NonFungibleTokenCollection } from "@adoptbitcoincash/bch-orm"
  export let nonFungibleTokenCollection : NonFungibleTokenCollection;
</script>