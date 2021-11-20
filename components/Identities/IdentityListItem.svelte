{#if identity.imageAvatar}
  <ListItem header={$_(header)} title="{identity.name}" link="/identities/{identity.id}">
    <img slot="media" class="message-avatar lazy" src={BCH.cdn.getImage(identity.imageAvatar)} width="40" alt="" />
  </ListItem>
{:else}
  <ListItem header={$_(header)} title="{identity.name}" link="/identities/{identity.id}">
    <i slot="media" class="f7-icons" style="font-size:28px;">person_alt_circle_fill</i>
  </ListItem>
{/if}

<style></style>

<script lang="ts">
  import { _ } from 'svelte-i18n';
  import { ListItem } from 'framework7-svelte';

  export let BCH;
  export let identityId: string;
  export let header: string;
  let identity = BCH.hub.identities.find(identityId);
</script>