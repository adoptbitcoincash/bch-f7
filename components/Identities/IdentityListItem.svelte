<ListItem header={$_(header)} title="{identity.name}" link="/profiles/{identity.id}">
  <img slot="media" class="message-avatar" src="{identity.avatarSmall.cdn}" width="40" alt="" />
</ListItem>

<style>
</style>

<script lang="ts">
  import { _ } from 'svelte-i18n';
  import { ListItem } from 'framework7-svelte';

  export let DB;
  export let identityId: string;
  export let header: string;
  let identity = DB.hub.identities.find(identityId);
</script>