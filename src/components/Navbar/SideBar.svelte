<script>
  import links from '../../constants/links.js'
  import {link} from 'svelte-routing';
  import globalStore from '../../stores/globalStore';
  import {fly, fade} from 'svelte/transition';
  import LoginLink from '../LoginLink.svelte';
  
</script>

<div class="sidebar-container" transition:fly={{ x:-1000 }}>
 <div class="sidebar" transition:fade={{ delay: 400}}>
   <!--Header-->
   <div class="sidebar-header">
     <button class="btn-close"  on:click={()=> globalStore.toggleItem('sidebar', false)}>
       <i class="fas fa-window-close" />
     </button>
   </div>
   <!--Site Logo-->
   <img src="/assets/images/logo.svg" alt="razers logo" class="logo sidebar-logo">
   <!-- Links -->
    <ul class='sidebar-links'>
      {#each links as sideLink}
       <li>
        <a href={sideLink.url} use:link on:click={()=> globalStore.toggleItem('sidebar', false)}>{sideLink.text}</a>
        </li>
      {/each}
      <li>
        <LoginLink/>
      </li>
    </ul>
  </div>
</div>