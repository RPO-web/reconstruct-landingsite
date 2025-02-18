<script lang="ts">
    import { navigationLinks } from "$lib/data/navigation";
    import { socialLinks } from "$lib/data/social";
    import { contactInfo } from "$lib/data/contact";

    const currentYear = $state(new Date().getFullYear());
</script>

<footer class="bg-primary-900 text-white">
    <div class="container mx-auto px-4 py-12">
        <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
            <!-- Company Info -->
            <div class="col-span-1 md:col-span-2">
                <h3 class="text-xl font-bold mb-4">
                    {contactInfo.companyName}
                </h3>
                <p class="text-primary-200 mb-4 max-w-md">
                    Making a difference through innovative solutions and
                    exceptional service.
                </p>
                <div class="flex space-x-4">
                    {#each socialLinks as link}
                        <a
                            href={link.href}
                            class="text-primary-200 hover:text-white transition-colors"
                        >
                            <span class="sr-only">{link.title}</span>
                            <svg
                                class="h-6 w-6"
                                fill="currentColor"
                                viewBox="0 0 24 24"
                            >
                                {@html link.icon}
                            </svg>
                        </a>
                    {/each}
                </div>
            </div>

            <!-- Quick Links -->
            <div>
                <h3 class="text-lg font-semibold mb-4">Quick Links</h3>
                <ul class="space-y-2">
                    {#each navigationLinks as link}
                        <li>
                            <a
                                href={link.href}
                                class="text-primary-200 hover:text-white transition-colors"
                            >
                                {link.title}
                            </a>
                        </li>
                    {/each}
                </ul>
            </div>

            <!-- Contact Info -->
            <div>
                <h3 class="text-lg font-semibold mb-4">Contact</h3>
                <ul class="space-y-2">
                    <li class="text-primary-200">
                        {contactInfo.address.street}
                    </li>
                    <li class="text-primary-200">
                        {contactInfo.address.cityState}
                    </li>
                    <li>
                        <a
                            href="tel:{contactInfo.phone.href}"
                            class="text-primary-200 hover:text-white transition-colors"
                        >
                            {contactInfo.phone.display}
                        </a>
                    </li>
                    <li>
                        <a
                            href="mailto:{contactInfo.email.href}"
                            class="text-primary-200 hover:text-white transition-colors"
                        >
                            {contactInfo.email.display}
                        </a>
                    </li>
                </ul>
            </div>
        </div>

        <!-- Copyright -->
        <div
            class="border-t border-primary-800 mt-12 pt-8 text-center text-primary-200"
        >
            <p>
                &copy; {currentYear}
                {contactInfo.companyName}. All rights reserved.
            </p>
        </div>
    </div>
</footer>
