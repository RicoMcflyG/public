<script>
   export let id;
   
   //global store
   import globalStore from '../stores/globalStore'
   import products from '../stores/defaultProducts';
   import Loading from '../components/Loading.svelte';
   import {link} from 'svelte-routing';
   import {addToCart} from '../stores/cart'
  import { get_all_dirty_from_scope } from 'svelte/internal';
   
   $: product = $products.find(item => item.id === parseInt(id));

</script>

<svelte:head>
   <title>{!product? 'single product' : product.title}</title>
</svelte:head>
{#if !product}
<Loading />
{:else}
<section class='single-product'>
<a href='/products' use:link class='btn btn-primary'>back to products</a>
<div class='single-product-container'>
<article class='single-product-image'>
<img src={product.image} alt={product.title}/>
<article>
   <h1>{product.title}</h1>
   <h2>${product.price}</h2>
   <p>{product.description}</p>
   <button class='btn btn-primary btn-block' on:click={()=> {
      addToCart(product),
      globalStore.toggleItem('cart', true)}}>add to cart</button>
</article>
</article>   
</div>
</section>
{/if} 
