{#if withMedia}
  <ListItem header={$_('collection')} title="{nonFungibleTokenCollection.name}" link="/nonFungibleTokenCollections/{nonFungibleTokenCollection.id}/details">
    <img slot="media" class="message-avatar" src="{nonFungibleTokenCollection.imageAvatar.cdn}" width="40" alt="" />
  </ListItem>
{:else}
  <ListItem header={$_('collection')} title="{nonFungibleTokenCollection.name}" link="/nonFungibleTokenCollections/{nonFungibleTokenCollection.id}/details"/>
{/if}

<style></style>

<script lang="ts">
  import { _ } from 'svelte-i18n';
  import { ListItem } from 'framework7-svelte';

  export let DB;
  export let nonFungibleTokenCollectionId: string;
  export let withMedia: boolean = false;
  let nonFungibleTokenCollection = DB.hub.nonFungibleTokenCollections.find(nonFungibleTokenCollectionId);
</script>