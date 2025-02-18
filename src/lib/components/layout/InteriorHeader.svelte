<script>
    import { navigationLinks } from "$lib/data/navigation";
    let isMenuOpen = $state(false);
</script>

<header class="fixed w-full py-4 top-0 left-0 right-0 z-50 bg-surface-100-900">
    <div class="container mx-auto px-4">
        <nav class="flex items-center justify-between">
            <a href="/" class="text-2xl font-bold text-surface-900-50">
                Logo
            </a>
            <!-- Desktop Navigation -->
            <div class="hidden md:flex items-center space-x-8">
                {#each navigationLinks as link}
                    <a
                        href={link.href}
                        class="text-surface-700-200 hover:text-secondary-900-100 transition-colors"
                    >
                        {link.title}
                    </a>
                {/each}
            </div>
            <!-- Mobile Menu Button -->
            <button
                type="button"
                class="md:hidden text-surface-900-50"
                onclick={() => (isMenuOpen = !isMenuOpen)}
                aria-expanded={isMenuOpen}
                aria-controls="mobile-menu"
                aria-label={isMenuOpen ? "Close menu" : "Open menu"}
            >
                <svg
                    class="w-6 h-6"
                    fill="none"
                    stroke="currentColor"
                    viewBox="0 0 24 24"
                    aria-hidden="true"
                >
                    <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width={2}
                        d="M4 6h16M4 12h16M4 18h16"
                    />
                </svg>
            </button>
        </nav>
        <!-- Mobile Menu -->
        {#if isMenuOpen}
            <div id="mobile-menu" class="md:hidden mt-4 space-y-4">
                {#each navigationLinks as link}
                    <a
                        href={link.href}
                        class="block text-surface-700-200 hover:text-primary-500 transition-colors"
                    >
                        {link.title}
                    </a>
                {/each}
                <!-- Contact Button -->
                <a
                    href="/contact"
                    class="block px-4 py-2 bg-primary-500 text-surface-50-950 rounded-lg hover:bg-primary-600 transition-colors text-center"
                >
                    Contact Us
                </a>
            </div>
        {/if}
    </div>
</header>
