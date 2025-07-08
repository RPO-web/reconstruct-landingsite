<script lang="ts">
    import { navigationLinks } from "$lib/data/navigation";
    import { services } from "$lib/data/services";
    let isMenuOpen = $state(false);
    let isServicesDropdownOpen = $state(false);
    let dropdownTimeout: number;

    function showDropdown() {
        clearTimeout(dropdownTimeout);
        isServicesDropdownOpen = true;
    }

    function hideDropdown() {
        dropdownTimeout = setTimeout(() => {
            isServicesDropdownOpen = false;
        }, 150); // 150ms delay
    }
</script>

<header class="fixed w-full py-4 top-0 left-0 right-0 z-50 bg-white/95 dark:bg-surface-900/95 backdrop-blur-sm border-b border-surface-200 dark:border-surface-700">
    <div class="container mx-auto px-4">
        <nav class="flex items-center justify-between">
            <a href="/" class="flex items-center">
                <img src="/demo/demologo.png" alt="Logo" class="h-8 w-auto" />
            </a>
            <!-- Desktop Navigation -->
            <div class="hidden md:flex items-center space-x-8">
                {#each navigationLinks as link}
                    {#if link.title === "Services"}
                        <div class="relative group">
                            <button
                                class="flex items-center text-surface-700 dark:text-surface-200 hover:text-primary-600 dark:hover:text-primary-400 transition-colors font-medium"
                                onmouseenter={showDropdown}
                                onmouseleave={hideDropdown}
                            >
                                Services
                                <svg class="w-4 h-4 ml-1" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path>
                                </svg>
                            </button>
                            {#if isServicesDropdownOpen}
                                <div 
                                    class="absolute top-full left-0 mt-1 w-80 bg-white dark:bg-surface-900 rounded-lg shadow-lg border border-surface-200 dark:border-surface-700 py-2 z-50"
                                    onmouseenter={showDropdown}
                                    onmouseleave={hideDropdown}
                                >
                                    <a href="/services" class="block px-4 py-2 text-sm text-surface-700 dark:text-surface-200 hover:bg-surface-100 dark:hover:bg-surface-800 font-medium border-b border-surface-200 dark:border-surface-700">
                                        All Services
                                    </a>
                                    {#each services as service}
                                        <a 
                                            href="/services/{service.slug}" 
                                            class="block px-4 py-3 text-sm text-surface-700 dark:text-surface-200 hover:bg-surface-100 dark:hover:bg-surface-800 transition-colors"
                                        >
                                            <div class="font-medium">{service.title}</div>
                                            <div class="text-xs text-surface-500 dark:text-surface-400 mt-1">
                                                {service.title === "Manufactured Housing Installation" ? "Turnkey home installations" :
                                                 service.title === "General Contracting" ? "Licensed residential & commercial" :
                                                 service.title === "Accessory Structures" ? "Sheds, garages, ADUs" :
                                                 "Raw land to shovel-ready lots"}
                                            </div>
                                        </a>
                                    {/each}
                                </div>
                            {/if}
                        </div>
                    {:else}
                        <a
                            href={link.href}
                            class="text-surface-700 dark:text-surface-200 hover:text-primary-600 dark:hover:text-primary-400 transition-colors font-medium"
                        >
                            {link.title}
                        </a>
                    {/if}
                {/each}
                <a
                    href="/contact"
                    class="px-4 py-2 bg-primary-500 text-white rounded-lg hover:bg-primary-600 transition-colors font-medium"
                >
                    Contact Us
                </a>
            </div>
            <!-- Mobile Menu Button -->
            <button
                type="button"
                class="md:hidden text-surface-900 dark:text-surface-50"
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
            <div id="mobile-menu" class="md:hidden mt-4 space-y-4 bg-white dark:bg-surface-900 rounded-lg p-4 shadow-lg border border-surface-200 dark:border-surface-700">
                <a
                    href="/services"
                    class="block text-surface-700 dark:text-surface-200 hover:text-primary-500 transition-colors font-medium"
                >
                    Services
                </a>
                {#each services as service}
                    <a
                        href="/services/{service.slug}"
                        class="block text-surface-600 dark:text-surface-300 hover:text-primary-500 transition-colors text-sm pl-4"
                    >
                        {service.title}
                    </a>
                {/each}
                <a
                    href="/company"
                    class="block text-surface-700 dark:text-surface-200 hover:text-primary-500 transition-colors font-medium"
                >
                    Company
                </a>
                <a
                    href="/hiring"
                    class="block text-surface-700 dark:text-surface-200 hover:text-primary-500 transition-colors font-medium"
                >
                    Hiring
                </a>
                <!-- Contact Button -->
                <a
                    href="/contact"
                    class="block px-4 py-2 bg-primary-500 text-white rounded-lg hover:bg-primary-600 transition-colors text-center font-medium"
                >
                    Contact Us
                </a>
            </div>
        {/if}
    </div>
</header>
