<script>
  import { AppShell } from '@skeletonlabs/skeleton';
  import { onMount } from 'svelte';
  import {sidebarOpen} from '../stores/SidebarStore'

  let isCartOpen = false;

  function toggleCart() {
    isCartOpen = !isCartOpen;
  }

  onMount(() => {
    const sidebar = document.querySelector('.sidebar');

    function handleResize() {
      if (window.innerWidth > 768) {
        sidebar.classList.remove('open');
        isCartOpen = false;
      }
    }

    window.addEventListener('resize', handleResize);

    return () => {
      window.removeEventListener('resize', handleResize);
    };
  });
</script>

<AppShell>

  <svelte:fragment slot="sidebarRight">
    <div class="sidebar" class:open={$sidebarOpen}>
      {#if isCartOpen}
        <div class="sidebar-content bg-gray-200 p-4">
          <h1>Cart Items</h1>
          <p>Display cart items, totals, and interactions here</p>
        </div>
      {:else}
        <div class="sidebar-placeholder bg-gray-300 p-4">
          <h1>Closed Cart</h1>
          <p>Display something when the cart is closed</p>
        </div>
      {/if}
    </div>
  </svelte:fragment>

  <slot />
</AppShell>

<style>
  .sidebar {
    transition: transform 0.3s ease-in-out;
    transform: translateX(100%);
    width: 400px;
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    background-color: white;
    overflow-y: auto;
  }

  .sidebar.open {
    transform: translateX(0);
  }

  /* Additional styling goes here */
</style>