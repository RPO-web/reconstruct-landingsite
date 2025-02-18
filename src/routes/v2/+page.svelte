<!-- Hero Section -->
<section class="relative pt-40 pb-32 bg-surface-100-800">
    <!-- Background Image with Overlay -->
    <div class="absolute inset-0 z-0" aria-hidden="true">
        <img
            src="/demo/hero-bg.jpg"
            alt="Hero background"
            class="w-full h-full object-cover opacity-20 dark:opacity-10"
        />
        <div
            class="absolute inset-0 bg-gradient-to-r from-primary-500/30 to-secondary-500/30"
        ></div>
    </div>

    <!-- Content -->
    <div class="container mx-auto px-4 relative z-10">
        <div class="max-w-4xl">
            <h2
                class="inline-block mb-6 px-4 py-1 bg-primary-100-900 rounded-full"
            >
                <span class="text-primary-800-200 font-medium">Welcome</span>
            </h2>
            <h1 class="text-5xl md:text-6xl font-bold text-surface-900-50 mb-6">
                Transform Your Vision Into
                <span class="text-primary-500">Reality</span>
            </h1>
            <p
                class="text-xl md:text-2xl text-surface-700-200 max-w-2xl leading-relaxed"
            >
                Your premier solution for innovative services and outstanding
                results.
            </p>
        </div>
    </div>
</section>

<!-- Services Section -->
<section class="py-24 bg-surface-50-900">
    <div class="container mx-auto px-4">
        <div class="text-center mb-12">
            <h2
                class="inline-block mb-6 px-4 py-1 bg-secondary-100-900 rounded-full"
            >
                <span class="text-secondary-800-200 font-medium"
                    >Our Services</span
                >
            </h2>
            <p class="text-3xl font-bold text-surface-900-50">
                Excellence in Every Detail
            </p>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mb-12">
            {#each Array(4) as _, i}
                <div class="group relative overflow-hidden rounded-xl">
                    <div class="relative" aria-hidden="true">
                        <img
                            src={`/demo/service-${i + 1}.jpg`}
                            alt="Professional service background"
                            class="w-full h-80 object-cover transition-transform duration-500 group-hover:scale-110"
                        />
                        <div
                            class="absolute inset-0 bg-gradient-to-t from-surface-900/80 to-surface-900/20 group-hover:from-surface-900/90 group-hover:to-surface-900/30 transition-all duration-300"
                        ></div>
                    </div>
                    <div class="absolute bottom-0 left-0 right-0 p-6">
                        <h3 class="text-2xl font-semibold text-surface-50 mb-2">
                            Service {i + 1}
                        </h3>
                        <p class="text-surface-200 mb-4 opacity-90">
                            Description for Service {i + 1}. Add your service
                            description here.
                        </p>
                        <a
                            href={`/services#service-${i + 1}`}
                            class="inline-flex items-center text-primary-400 hover:text-primary-300 font-medium group-hover:gap-2 transition-all"
                        >
                            Learn more
                            <svg
                                aria-hidden="true"
                                class="w-5 h-5 ml-1 transition-transform group-hover:translate-x-1"
                                fill="none"
                                stroke="currentColor"
                                viewBox="0 0 24 24"
                            >
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    d="M17 8l4 4m0 0l-4 4m4-4H3"
                                />
                            </svg>
                        </a>
                    </div>
                </div>
            {/each}
        </div>
        <div class="text-center">
            <a
                href="/services"
                class="inline-flex items-center px-6 py-3 bg-primary-500 text-white rounded-lg hover:bg-primary-600 transition-colors duration-300"
            >
                View All Services
                <svg
                    aria-hidden="true"
                    class="w-5 h-5 ml-2"
                    fill="none"
                    stroke="currentColor"
                    viewBox="0 0 24 24"
                >
                    <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M17 8l4 4m0 0l-4 4m4-4H3"
                    />
                </svg>
            </a>
        </div>
    </div>
</section>

<!-- About & Careers Cards Section -->
<section class="py-24 bg-surface-100-800 relative overflow-hidden">
    <div class="absolute inset-0" aria-hidden="true">
        <div
            class="absolute inset-0 bg-gradient-to-r from-primary-500/10 to-secondary-500/10"
        ></div>
    </div>
    <div class="container mx-auto px-4 relative z-10">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
            <!-- About Us Card -->
            <div class="group">
                <div
                    class="bg-surface-50-900 p-8 rounded-xl shadow-sm hover:shadow-md transition-all duration-300 h-full border border-surface-200-700 relative overflow-hidden"
                >
                    <div
                        class="absolute inset-0 bg-primary-500/0 group-hover:bg-primary-500/5 transition-colors duration-300"
                        aria-hidden="true"
                    ></div>
                    <div class="relative">
                        <h2
                            class="text-2xl font-semibold text-surface-900-50 mb-4"
                        >
                            About Us
                        </h2>
                        <p class="text-surface-700-200 mb-6 leading-relaxed">
                            Discover our story and what makes us different.
                        </p>
                        <a
                            href="/company"
                            class="inline-flex items-center text-primary-600 dark:text-primary-400 hover:text-primary-700 dark:hover:text-primary-300 font-medium group-hover:gap-2 transition-all"
                        >
                            Learn more
                            <svg
                                aria-hidden="true"
                                class="w-5 h-5 ml-1 transition-transform group-hover:translate-x-1"
                                fill="none"
                                stroke="currentColor"
                                viewBox="0 0 24 24"
                            >
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    d="M17 8l4 4m0 0l-4 4m4-4H3"
                                />
                            </svg>
                        </a>
                    </div>
                </div>
            </div>

            <!-- Careers Card -->
            <div class="group">
                <div
                    class="bg-surface-50-900 p-8 rounded-xl shadow-sm hover:shadow-md transition-all duration-300 h-full border border-surface-200-700 relative overflow-hidden"
                >
                    <div
                        class="absolute inset-0 bg-secondary-500/0 group-hover:bg-secondary-500/5 transition-colors duration-300"
                        aria-hidden="true"
                    ></div>
                    <div class="relative">
                        <h2
                            class="text-2xl font-semibold text-surface-900-50 mb-4"
                        >
                            Careers
                        </h2>
                        <p class="text-surface-700-200 mb-6 leading-relaxed">
                            Join our team and be part of something great.
                        </p>
                        <a
                            href="/careers"
                            class="inline-flex items-center text-secondary-600 dark:text-secondary-400 hover:text-secondary-700 dark:hover:text-secondary-300 font-medium group-hover:gap-2 transition-all"
                        >
                            Learn more
                            <svg
                                aria-hidden="true"
                                class="w-5 h-5 ml-1 transition-transform group-hover:translate-x-1"
                                fill="none"
                                stroke="currentColor"
                                viewBox="0 0 24 24"
                            >
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    d="M17 8l4 4m0 0l-4 4m4-4H3"
                                />
                            </svg>
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- Contact Section -->
<section class="py-24 bg-surface-50-900">
    <div class="container mx-auto px-4">
        <div class="max-w-2xl mx-auto text-center mb-12">
            <div
                class="inline-block mb-6 px-4 py-1 bg-primary-100 dark:bg-primary-900/30 rounded-full"
            >
                <span class="text-primary-600 dark:text-primary-400 font-medium"
                    >Get In Touch</span
                >
            </div>
            <h2 class="text-3xl font-bold text-surface-900-50 mb-4">
                Let's Build Something
                <span class="text-primary-500">Together</span>
            </h2>
            <p class="text-xl text-surface-700-200">
                Have a question or want to learn more? We'd love to hear from
                you.
            </p>
        </div>
        <div class="max-w-xl mx-auto">
            <div
                class="bg-surface-50-900 p-8 rounded-xl shadow-sm border border-surface-200-700"
            >
                <p class="text-lg text-surface-700-200 mb-6">
                    Tell us about your project or ask us any questions using our
                    contact form.
                </p>
                <a
                    href="/contact"
                    class="inline-flex w-full items-center justify-center px-8 py-4 bg-primary-500 text-white rounded-lg hover:bg-primary-600 transition-colors duration-300 font-medium group gap-2"
                >
                    Contact Form
                    <svg
                        class="w-5 h-5 transition-transform group-hover:translate-x-1"
                        fill="none"
                        stroke="currentColor"
                        viewBox="0 0 24 24"
                    >
                        <path
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            stroke-width="2"
                            d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14"
                        />
                    </svg>
                </a>
                <p class="mt-4 text-sm text-surface-700-200 text-center">
                    Contact us today to get started
                </p>
            </div>
        </div>
    </div>
</section>
