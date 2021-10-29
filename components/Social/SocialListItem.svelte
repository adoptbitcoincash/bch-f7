{#if display && type == 'artstation'}
<ListItem title={$_('social.artstation')}>
  <Link slot="after" href="https://artstation.com/{social[type]}" target="_blank" external iconF7="paintbrush"></Link>
</ListItem>
{/if}

{#if display && type == 'discord'}
<ListItem title={$_('social.discord')}>
  <Link slot="after" href="https://discord.gg/{social[type]}" target="_blank" external iconF7="chat_bubble_2"></Link>
</ListItem>
{/if}

{#if display && type == 'email'}
<ListItem title={$_('social.email')}>
  <Link slot="after" href="mailto:{social[type]}" target="_blank" external iconF7="envelope"></Link>
</ListItem>
{/if}

{#if display && type == 'facebook'}
<ListItem title={$_('social.facebook')}>
  <Link slot="after" href="https://facebook.com/{social[type]}" target="_blank" external iconF7="logo_facebook"></Link>
</ListItem>
{/if}

{#if display && type == 'instagram'}
<ListItem title={$_('social.instagram')}>
  <Link slot="after" href="https://instagram.gg/{social[type]}" target="_blank" external iconF7="logo_instagram"></Link>
</ListItem>
{/if}

{#if display && type == 'telegram'}
<ListItem title={$_('social.telegram')}>
  <Link slot="after" href="https://telegram.com/{social[type]}" target="_blank" external iconF7="macwindow"></Link>
</ListItem>
{/if}

{#if display && type == 'twitter'}
<ListItem title={$_('social.twitter')}>
  <Link slot="after" href="https://twitter.com/{social[type]}" target="_blank" external iconF7="logo_twitter"></Link>
</ListItem>
{/if}

{#if display && type == 'website'}
<ListItem title={$_('social.website')}>
  <Link slot="after" href="https://{social[type]}" target="_blank" external>{social[type]}</Link>
</ListItem>
{/if}

{#if display && type == 'youtube'}
<ListItem title={$_('social.youtube')}>
  <Link slot="after" href="https://youtube.com/{social[type]}" target="_blank" external iconF7="videocam"></Link>
</ListItem>
{/if}

<script lang="ts">
  import { _ } from 'svelte-i18n';
  import { ListItem, Link } from 'framework7-svelte';
  import type { SocialDatas } from "@adoptbitcoincash/bch-orm";

  export let social : SocialDatas;
  export let type: string;
  let display = social[type] && social[type].length > 0;
</script>