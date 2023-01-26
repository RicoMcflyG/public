<script>
  export let title ='';
  // import {onMount, onDestroy} from 'svelte';
  import products from '../../stores/defaultProducts';
  import Product from '../Products/Product.svelte';
  import Loading from '../Loading.svelte';

  // let localProducts =[];
  // let unsubscribe;

  // onMount(()=>{
  //   unsubscribe = products.subscribe(value => {
  //     console.log(products);

  //     localProducts = value;
  //   })
  // })
  // onDestroy(() => {
  //   unsubscribe();
  // })
</script>

<section class='section'>
<h2 class='section-title'>{title}</h2>
<div class='products-center'>
{#each $products as product}
<Product {product}/>
{:else}
<Loading />
{/each}
</div>
</section>