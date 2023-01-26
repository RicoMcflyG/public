<script>
  //cart button 
  import CartButton from '../Cart/CartButton.svelte';
  import {link} from 'svelte-routing'; 
  //global store
  import globalStore from '../../stores/globalStore';
  let openSidebar = globalStore.toggleItem;

 
</script>

<nav class='navbar'>
  <div class='nav-center'>
    <!--Sidebar Logo-->
  <button class='btn-sidebar-toggle' on:click={() => {
    openSidebar('sidebar', true)
  }}>
  <i class='fas fa-bars'></i>  
  </button>
  <!--Logo-->
  <a href='/' use:link class='nav-logo'>
    <img src='/assets/images/logo.svg'class='logo' alt='razers logo'>
    </a>
    <!--Cart Button-->
   <CartButton  />
    
  </div>
</nav>