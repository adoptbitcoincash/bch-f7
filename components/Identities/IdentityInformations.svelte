<BlockTitle>Informations</BlockTitle>
<List>
  <ListItem title="Name" after={identity.name}/>
  <Social social={identity.social}/>
</List>

<script lang="ts">
  import { BlockTitle, List, ListItem } from 'framework7-svelte';
  import Social from '../Social/Social.svelte';
  import type { Identity } from "@adoptbitcoincash/bch-orm"
  export let identity : Identity;
</script>