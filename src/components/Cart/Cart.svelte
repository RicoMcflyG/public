<script>
  import globalStore from '../../stores/globalStore';
  import {fly, fade, blur} from 'svelte/transition';
  import {link} from 'svelte-routing';
  //item list
  import ItemList from './ItemList.svelte';
  //dummy user
  import user from '../../stores/User'
</script>

<div class="cart-overlay" transition:blur >
  <div class="cart-container" transition:fly={{x:100}} >
    <div class="cart" transition:fade={{delay:400}}>
      <!--Cart header -->
    <div class="cart-header">
      <button class="btn-close" on:click={()=>{globalStore.toggleItem('cart', false)}}>
        <i class="fas fa-window-close"></i>
      </button>
      <h2 class="cart-title">your bag</h2>
      <span></span>
    </div>
    <!--End of cart header-->

    <!--Cart items-->
    <ItemList/>
    <!--End of cart items-->
    <!--Cart Footer-->
    <div class="cart-footer">
      {#if $user.jwt}
      <a href="/checkout" class="btn btn-primary btn-block" on:click={()=> globalStore.toggleItem('cart', false)}>Checkout</a>
      {:else}
      <p class="cart-login">
        in order to checkout please
        <a href="/checkout" use:link on:click={()=> globalStore.toggleItem('cart', false)}>LOGIN</a>
      </p>
      {/if}

    </div>
    <!--End of Cart Footer-->
    </div>
  </div>
</div>

