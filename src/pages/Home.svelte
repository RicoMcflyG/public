<script>
  import Hero from '../components/Hero.svelte';
  import {link} from 'svelte-routing';
  import Featured from '../components/Products/Featured.svelte';

  //featured products

</script>



<Hero>
<!--Shop now button-->
<a href='/products' class='btn btn-primary btn-hero' use:link>Shop Now</a>
</Hero>
<Featured />