<SocialListItem type="website" social={social}/>
<SocialListItem type="email" social={social}/>
<SocialListItem type="artstation" social={social}/>
<SocialListItem type="discord" social={social}/>
<SocialListItem type="facebook" social={social}/>
<SocialListItem type="telegram" social={social}/>
<SocialListItem type="instagram" social={social}/>
<SocialListItem type="twitter" social={social}/>
<SocialListItem type="youtube" social={social}/>

<script lang="ts">
  import SocialListItem from './SocialListItem.svelte';
  import type { SocialDatas } from "@adoptbitcoincash/bch-orm"
  export let social : SocialDatas;
</script>