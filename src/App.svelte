<script>
//pages
import About from './pages/About.svelte'
import Checkout from './pages/Checkout.svelte'
import Home from './pages/Home.svelte'
import Login from './pages/Login.svelte'
import Products from './pages/Products.svelte'
import ProductTemplate from './pages/ProductTemplate.svelte'
import Navbar from './components/Navbar/Navbar.svelte'
import SideBar from './components/Navbar/SideBar.svelte'
import Cart from './components/Cart/Cart.svelte'
//global store
import globalStore from './stores/globalStore'
console.log(globalStore);
console.log($globalStore);

//router
import {Router, Link, Route} from 'svelte-routing'

</script>

<Router>
<Navbar />
{#if $globalStore.sidebar}
<SideBar />
{/if}
{#if $globalStore.cart}
<Cart />
{/if}
<Route path='/' component={Home}/>
<Route path='/about' component={About}/>
<Route path='/login' component={Login}/>
<Route path='/products' component={Products}/>
<Route path='/products/:id' component={ProductTemplate}/>
</Router>