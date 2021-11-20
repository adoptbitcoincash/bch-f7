{#if withMedia}
  <ListItem header={$_('collection')} title="{nftCollection.name}" link="/nftCollections/{nftCollection.id}/details">
    <img slot="media" class="message-avatar" src={BCH.cdn.getImage(nftCollection.imageAvatar)} width="40" alt="" />
  </ListItem>
{:else}
  <ListItem header={$_('collection')} title="{nftCollection.name}" link="/nftCollections/{nftCollection.id}/details"/>
{/if}

<style></style>

<script lang="ts">
  import { _ } from 'svelte-i18n';
  import { ListItem } from 'framework7-svelte';

  export let BCH;
  export let nftCollectionId: string;
  export let withMedia: boolean = false;
  let nftCollection = BCH.hub.nftCollections.find(nftCollectionId);
</script>