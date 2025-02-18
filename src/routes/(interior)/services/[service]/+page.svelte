<script lang="ts">
    import { page } from "$app/stores";
    import { services } from "$lib/data/services";
    import { fade } from "svelte/transition";

    // Get the service based on the slug
    $: service = services.find((s) => s.slug === $page.params.service);
</script>

<!-- Hero Section -->
<div
    class="relative overflow-hidden pt-20 bg-surface-100-800 min-h-[300px] flex items-center"
>
    <div class="absolute inset-0">
        <img
            src={service?.image}
            alt={service?.title}
            class="w-full h-full object-cover opacity-20 dark:opacity-10"
        />
        <div
            class="absolute inset-0 bg-gradient-to-r from-primary-500/30 to-secondary-500/30"
        ></div>
    </div>
    <div class="container mx-auto px-4 py-12 relative z-10">
        <div class="max-w-3xl">
            <div
                class="inline-block mb-6 px-4 py-1 bg-primary-100 dark:bg-primary-900/30 rounded-full"
            >
                <span class="text-primary-600 dark:text-primary-400 font-medium"
                    >Our Services</span
                >
            </div>
            <h1 class="text-5xl md:text-6xl font-bold text-surface-900-50 mb-6">
                {service?.title}
            </h1>
            <p class="text-xl md:text-2xl text-surface-700-200">
                {service?.description}
            </p>
        </div>
    </div>
</div>

<!-- Main Content -->
<div class="container mx-auto px-4 py-16">
    <!-- Benefits Section -->
    <section class="mb-20">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-start">
            <div class="relative">
                <div class="relative z-10">
                    <img
                        src={service?.image}
                        alt={service?.title}
                        class="rounded-2xl shadow-lg w-full h-auto"
                    />
                </div>
                <div
                    class="absolute top-4 -right-4 w-full h-full bg-secondary-500/20 rounded-2xl -z-0"
                ></div>
                <div
                    class="absolute -bottom-4 -left-4 w-full h-full bg-primary-500/20 rounded-2xl -z-0"
                ></div>
            </div>
            <div>
                <div class="space-y-6">
                    <h2 class="text-3xl font-bold text-surface-900-50">
                        Key <span class="text-primary-500">Benefits</span>
                    </h2>
                    <div class="grid gap-4">
                        {#each service?.benefits || [] as benefit}
                            <div
                                class="flex items-start gap-4 p-4 bg-surface-50-900 rounded-lg border border-surface-200-700 hover:shadow-md transition-shadow"
                            >
                                <div class="text-primary-500 mt-1">
                                    <svg
                                        class="w-5 h-5"
                                        fill="none"
                                        stroke="currentColor"
                                        viewBox="0 0 24 24"
                                    >
                                        <path
                                            stroke-linecap="round"
                                            stroke-linejoin="round"
                                            stroke-width="2"
                                            d="M5 13l4 4L19 7"
                                        ></path>
                                    </svg>
                                </div>
                                <p class="text-surface-700-200">{benefit}</p>
                            </div>
                        {/each}
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Process Section -->
    <section>
        <div class="text-center mb-12">
            <div
                class="inline-block mb-6 px-4 py-1 bg-secondary-100 dark:bg-secondary-900/30 rounded-full"
            >
                <span
                    class="text-secondary-600 dark:text-secondary-400 font-medium"
                    >Our Process</span
                >
            </div>
            <h2 class="text-3xl font-bold text-surface-900-50">
                How We <span class="text-secondary-500">Deliver</span>
            </h2>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
            {#each service?.process || [] as step}
                <div class="group relative">
                    <div
                        class="absolute -inset-0.5 bg-gradient-to-r from-primary-500 to-secondary-500 rounded-lg opacity-20 group-hover:opacity-100 transition-opacity"
                    ></div>
                    <div
                        class="relative bg-surface-50-900 p-6 rounded-lg border border-surface-200-700"
                    >
                        <div class="flex items-center gap-4 mb-4">
                            <div
                                class="w-8 h-8 rounded-full bg-primary-500 flex items-center justify-center text-surface-50 font-bold"
                            >
                                {step.step}
                            </div>
                            <h3
                                class="text-xl font-semibold text-surface-900-50"
                            >
                                {step.title}
                            </h3>
                        </div>
                        <p class="text-surface-700-200">{step.description}</p>
                    </div>
                </div>
            {/each}
        </div>
    </section>
</div>
