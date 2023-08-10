<script>
	import { AppBar } from '@skeletonlabs/skeleton';
  import {toggleSidebar} from '../stores/SidebarStore'

	let isMobileMenuOpen = false;

	const menuItems = [
		{ label: 'Home', link: '/' },
		{ label: 'Purchases', link: '/purchases' },
		// { label: 'Cart' },
		{ label: 'Login', link: '/login' }
	];

	function toggleMobileMenu() {
		isMobileMenuOpen = !isMobileMenuOpen;
	}
</script>

<AppBar>
	<button
		class="hamburger-icon cursor-pointer md:hidden"
		type="button"
		aria-label="Toggle Mobile Menu"
		on:click={toggleMobileMenu}
	>
		<span class="block h-1 w-6 bg-gray-500 mb-1" />
		<span class="block h-1 w-6 bg-gray-500 mb-1" />
		<span class="block h-1 w-6 bg-gray-500" />
	</button>

	<nav class="list-nav">
		<ul class:desktop-menu={!isMobileMenuOpen} class:mobile-menu-active={isMobileMenuOpen}>
			{#each menuItems as menuItem}
				<!-- {#if menuItem.label !== 'Cart'} -->
					<li>
						<a href={menuItem.link} on:click={() => (isMobileMenuOpen = false)}>
							<span class="menu-item">{menuItem.label}</span>
						</a>
					</li>
				<!-- {:else}
					<li>
						<button class="menu-item-button" on:click={toggleSidebar}>
							Cart
						</button>
					</li>
				{/if} -->
			{/each}
		</ul>
	</nav>
</AppBar>

<style>
	.mobile-menu-active {
		display: none;
		position: absolute;
		top: 100%;
		left: 0;
		background-color: white;
		box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1);
		width: 100%;
		opacity: 0;
		max-height: 0;
		overflow: hidden;
	}

	.mobile-menu-active {
		transition: opacity 0.3s, max-height 0.3s;
		display: flex;
		flex-direction: column;
		opacity: 1;
		max-height: 100vh;
		overflow: visible;
	}

	@media (min-width: 769px) {
		.mobile-menu-active {
			display: none;
		}

		.desktop-menu {
			display: flex;
			/* Add your horizontal layout styles here */
		}
	}
</style>
