<script lang="ts">
	import { Github, Zap, Menu, X } from '@lucide/svelte';
	import { Button } from 'bits-ui';
	import { page } from '$app/stores';
	import { slide } from 'svelte/transition';
	import { cubicOut } from 'svelte/easing';

	const base = import.meta.env.BASE_URL.slice(0, -1); // Remove trailing slash

	let currentPath = $derived($page.url.pathname);
	let mobileMenuOpen = $state(false);

	function toggleMobileMenu() {
		mobileMenuOpen = !mobileMenuOpen;
	}

	function closeMobileMenu() {
		mobileMenuOpen = false;
	}
</script>

<nav class="navbar">
	<div class="navbar-content">
		<!-- Logo/Icon on the left -->
		<a href="/" onclick={closeMobileMenu}>
			<img src="/Logo.svg" alt="kiloJoule Logo" class="logo-icon" />
		</a>

		<!-- Center navigation links (desktop) -->
		<div class="nav-center">
			<a class="navlink" class:active={currentPath === '/waitlist'} href="{base}/waitlist">Waitlist</a>
			<a class="navlink" class:active={currentPath === '/docs'} href="{base}/docs">Docs</a>
			<a class="navlink" class:active={currentPath === '/blog'} href="{base}/blog">Blog</a>
                        <a class="navlink" class:active={currentPath === '/integral'} href="{base}/integral">Integral</a>
		</div>

		<!-- Right side: Login button + GitHub icon (desktop) -->
		<div class="nav-right">
			<Button.Root class="login-button">
				<a href="#login" class="login-link">Login</a>
			</Button.Root>
			<a href="#github" class="icon-link" aria-label="GitHub">
				<Github class="icon" />
			</a>
		</div>

		<!-- Mobile menu button -->
		<button class="mobile-menu-button" onclick={toggleMobileMenu} aria-label="Toggle menu">
			{#if mobileMenuOpen}
				<X size={24} />
			{:else}
				<Menu size={24} />
			{/if}
		</button>
	</div>

	<!-- Mobile menu -->
	{#if mobileMenuOpen}
		<div class="mobile-menu" transition:slide={{ duration: 300, easing: cubicOut }}>
			<a class="mobile-navlink" class:active={currentPath === '/waitlist'} href="/waitlist" onclick={closeMobileMenu}>
				Waitlist
			</a>
			<a class="mobile-navlink" class:active={currentPath === '/docs'} href="/docs" onclick={closeMobileMenu}>
				Docs
			</a>
                        <a class="mobile-navlink" class:active={currentPath === '/blog'} href="/blog" onclick={closeMobileMenu}>
				Blog
			</a>
                        <a class="mobile-navlink" class:active={currentPath === '/integral'} href="/integral" onclick={closeMobileMenu}>
				Integral
			</a>
			<a href="#login" class="mobile-login-button" onclick={closeMobileMenu}>
				Login
			</a>
			<a href="#github" class="mobile-github-link" onclick={closeMobileMenu}>
				<Github size={20} />
				<span>GitHub</span>
			</a>
		</div>
	{/if}
</nav>

<style>
	.navbar {
		background: #ffffff;
		border-radius: 1rem;
		box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
		position: fixed;
		top: 0;
                left: 0;
                right: 0;
		z-index: 50;
		margin: 1rem 2rem 0 2rem;
		border: 1px solid #f1f5f9;
	}

	.navbar-content {
		max-width: 1280px;
		margin: 0 auto;
		padding: 1rem 1rem;
		display: flex;
		align-items: center;
		justify-content: space-between;
		gap: 2rem;
	}

        .logo-icon {
                height: 36px;
                display: flex;
	}

	.nav-center {
		display: flex;
		align-items: center;
		gap: 2rem;
		flex: 1;
		justify-content: center;
	}

	.navlink {
		color: #64748b;
		text-decoration: none;
		font-size: 0.95rem;
		font-weight: 500;
		transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
		position: relative;
		padding: 0.5rem 1rem;
		border-radius: 0.25rem;
	}

	.navlink:hover {
		color: #0f172a;
	}

	.navlink::before {
		content: '';
		position: absolute;
		inset: 0;
		border: 2px solid #3b82f6;
		border-radius: 0.25rem;
		opacity: 0;
		transform: scale(0.95);
		transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
	}

	.navlink:hover::before {
		opacity: 1;
		transform: scale(1);
		box-shadow: 0 0 12px rgba(59, 130, 246, 0.4);
	}

	/* Active state for current page */
	.navlink.active {
		color: #3b82f6;
		font-weight: 600;
	}

	.nav-right {
		display: flex;
		align-items: center;
		gap: 2rem;
	}

	.nav-right :global(.login-button) {
		background: #3b82f6;
		color: white;
		padding: 0.5rem 1.5rem;
		border-radius: 0.375rem;
		border: none;
		font-weight: 500;
		font-size: 0.95rem;
		transition: all 0.2s;
		cursor: pointer;
	}

	.nav-right :global(.login-button:hover) {
		background: #2563eb;
		transform: translateY(-1px);
		box-shadow: 0 4px 12px rgba(59, 130, 246, 0.3);
	}

	.login-link {
		text-decoration: none;
		color: inherit;
	}

	.icon-link {
		color: #64748b;
		transition: color 0.2s;
		display: flex;
		align-items: center;
	}

	.icon-link:hover {
		color: #3b82f6;
	}

	.icon-link :global(.icon) {
		width: 22px;
		height: 22px;
	}

	/* Mobile menu button */
	.mobile-menu-button {
		display: none;
		background: none;
		border: none;
		color: #0f172a;
		cursor: pointer;
		padding: 0.5rem;
		transition: color 0.2s;
	}

	.mobile-menu-button:hover {
		color: #3b82f6;
	}

	/* Mobile menu */
	.mobile-menu {
		display: none;
		flex-direction: column;
		gap: 0.5rem;
		padding: 1rem 2rem 2rem;
		background: #ffffff;
		border-top: 1px solid #f1f5f9;
		border-radius: 0 0 1rem 1rem;
	}

	.mobile-navlink {
		color: #64748b;
		text-decoration: none;
		font-size: 1.05rem;
		font-weight: 500;
		padding: 0.75rem 1rem;
		border-radius: 0.375rem;
		transition: all 0.2s;
		position: relative;
	}

	.mobile-navlink:hover {
		background: #f8fafc;
		color: #0f172a;
	}

	/* Mobile frame effect */
	.mobile-navlink::before {
		content: '';
		position: absolute;
		inset: 0;
		border: 2px solid #3b82f6;
		border-radius: 0.375rem;
		opacity: 0;
		transition: opacity 0.2s;
	}

	.mobile-navlink:hover::before {
		opacity: 1;
	}

	.mobile-navlink.active {
		color: #3b82f6;
		font-weight: 600;
	}

	.mobile-login-button {
		background: #3b82f6;
		color: white;
		padding: 0.75rem 1.5rem;
		border-radius: 0.375rem;
		text-decoration: none;
		font-weight: 600;
		font-size: 1rem;
		text-align: center;
		margin-top: 0.5rem;
		transition: all 0.2s;
	}

	.mobile-login-button:hover {
		background: #2563eb;
	}

	.mobile-github-link {
		display: flex;
		align-items: center;
		gap: 0.5rem;
		color: #64748b;
		text-decoration: none;
		font-weight: 500;
		padding: 0.75rem 1rem;
		border-radius: 0.375rem;
		transition: all 0.2s;
	}

	.mobile-github-link:hover {
		background: #f8fafc;
		color: #3b82f6;
	}

	/* Responsive design */
	@media (max-width: 768px) {
		.navbar {
			margin: 0.5rem 1rem 0 1rem;
		}

		.nav-center {
			display: none;
		}

		.nav-right {
			display: none;
		}

		.mobile-menu-button {
			display: block;
		}

		.mobile-menu {
			display: flex;
		}

		.navbar-content {
			padding: 1rem;
		}
	}
</style>
