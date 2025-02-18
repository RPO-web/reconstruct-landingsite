<script>
    import { services } from "$lib/data/services";
</script>

<div class="py-24 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 px-4">
    {#each services as service}
        <a
            href="/services/{service.slug}"
            class="group bg-surface hover:bg-primary-50 transition-all duration-300 p-6 rounded-lg shadow-md hover:shadow-lg block"
        >
            <div class="overflow-hidden rounded-lg mb-4">
                <img
                    src={service.image}
                    alt={service.title}
                    class="w-full h-48 object-cover transform transition-transform duration-300 group-hover:scale-105"
                />
            </div>
            <h3 class="text-2xl font-semibold text-primary-700 mb-2">
                {service.title}
            </h3>
            <p class="text-surface-700-200 mb-4">
                {service.description}
            </p>
            <div class="flex items-center text-primary-600 font-medium">
                <span>Learn More</span>
                <svg
                    class="w-5 h-5 ml-2 transform transition-transform group-hover:translate-x-1"
                    fill="none"
                    stroke="currentColor"
                    viewBox="0 0 24 24"
                >
                    <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M13 7l5 5-5 5M5 7l5 5-5 5"
                    />
                </svg>
            </div>
        </a>
    {/each}
</div>
