<script lang="ts">
    import { fade } from "svelte/transition";
</script>

<!-- Hero Section with Gradient Overlay -->
<div
    class="relative overflow-hidden bg-surface-100-800 min-h-[400px] flex items-center"
>
    <div class="absolute inset-0">
        <img
            src="/demo/hero-2.jpg"
            alt="Construction site panorama"
            class="w-full h-full object-cover opacity-20 dark:opacity-10"
        />
        <div
            class="absolute inset-0 bg-gradient-to-r from-primary-500/30 to-secondary-500/30"
        ></div>
    </div>
    <div class="container mx-auto px-4 py-12 relative z-10">
        <div class="max-w-3xl">
            <h1 class="text-5xl md:text-6xl font-bold text-surface-900-50 mb-6">
                Building Your
                <span class="text-primary-500">Future</span>
            </h1>
            <p class="text-xl md:text-2xl text-surface-700-200">
                With over 25 years of excellence in construction, we're
                committed to bringing your vision to life with precision and
                quality.
            </p>
        </div>
    </div>
</div>

<!-- Main Content -->
<div class="container mx-auto px-4 py-12">
    <!-- Company Overview Section with Accent -->
    <section class="mb-20">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
            <div>
                <div
                    class="inline-block mb-6 px-4 py-1 bg-primary-100 dark:bg-primary-900/30 rounded-full"
                >
                    <span
                        class="text-primary-600 dark:text-primary-400 font-medium"
                        >Our Foundation</span
                    >
                </div>
                <h2 class="text-3xl font-bold text-surface-900-50 mb-6">
                    A passion for
                    <span class="text-primary-500">Excellence</span>
                </h2>
                <p class="text-surface-700-200 mb-6 leading-relaxed">
                    Since 2015, we've been building more than just structures –
                    we've been building trust. Our journey began with small
                    residential projects and has grown to encompass major
                    commercial developments, industrial facilities, and
                    infrastructure projects.
                </p>
                <p class="text-surface-700-200 leading-relaxed">
                    Today, we're proud to be one of the region's most trusted
                    construction companies, known for our commitment to safety,
                    quality, and innovation in every project we undertake.
                </p>
            </div>
            <div class="relative">
                <div class="relative z-10">
                    <img
                        src="/demo/service-4.jpg"
                        alt="Our construction team at work"
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
        </div>
    </section>

    <!-- Values Section with Hover Effects -->
    <section class="mb-20">
        <div class="text-center mb-12">
            <div
                class="inline-block mb-6 px-4 py-1 bg-secondary-100 dark:bg-secondary-900/30 rounded-full"
            >
                <span
                    class="text-secondary-600 dark:text-secondary-400 font-medium"
                    >Our Values</span
                >
            </div>
            <h2 class="text-3xl font-bold text-surface-900-50">
                Building on Strong Principles
            </h2>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
            {#each [{ title: "Safety First", description: "We maintain the highest safety standards on every job site, protecting our team and your investment.", icon: "🛡️", color: "primary" }, { title: "Quality Craftsmanship", description: "Our experienced team delivers exceptional workmanship on every project, big or small.", icon: "🏗️", color: "secondary" }, { title: "Sustainability", description: "We're committed to eco-friendly construction practices and LEED-certified building methods.", icon: "🌱", color: "primary" }] as value}
                <div
                    class="group bg-surface-50-900 p-8 rounded-xl shadow-sm hover:shadow-md transition-all duration-300 border border-surface-200-700 relative overflow-hidden"
                >
                    <div
                        class="absolute inset-0 bg-{value.color}-500/0 group-hover:bg-{value.color}-500/5 transition-colors duration-300"
                    ></div>
                    <div class="relative">
                        <div class="text-4xl mb-4">{value.icon}</div>
                        <h3
                            class="text-xl font-semibold text-surface-900-50 mb-4"
                        >
                            {value.title}
                        </h3>
                        <p class="text-surface-700-200">{value.description}</p>
                    </div>
                </div>
            {/each}
        </div>
    </section>

    <!-- Team Section with Enhanced Cards -->
    <section class="mb-20">
        <div class="text-center mb-12">
            <div
                class="inline-block mb-6 px-4 py-1 bg-primary-100 dark:bg-primary-900/30 rounded-full"
            >
                <span class="text-primary-600 dark:text-primary-400 font-medium"
                    >Our Leadership</span
                >
            </div>
            <h2 class="text-3xl font-bold text-surface-900-50">
                Expert Team, Exceptional Results
            </h2>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
            {#each [{ name: "Robert Miller", position: "President & Lead Constructor", image: "/demo/team-1.jpg" }, { name: "Lisa Rodriguez", position: "Head of Project Management", image: "/demo/team-2.jpg" }, { name: "James Chen", position: "Chief Safety Officer", image: "/demo/team-3.jpg" }] as member}
                <div class="group">
                    <div class="relative overflow-hidden rounded-xl mb-4">
                        <img
                            src={member.image}
                            alt={member.name}
                            class="w-full aspect-square object-cover transition-transform duration-500 group-hover:scale-110"
                        />
                        <div
                            class="absolute inset-0 bg-gradient-to-t from-surface-900/60 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300"
                        ></div>
                        <div
                            class="absolute inset-0 flex items-end p-6 opacity-0 group-hover:opacity-100 transition-opacity duration-300"
                        >
                            <p class="text-surface-50 text-sm">
                                View Profile →
                            </p>
                        </div>
                    </div>
                    <h3 class="text-xl font-semibold text-surface-900-50 mb-2">
                        {member.name}
                    </h3>
                    <p class="text-surface-700-200">{member.position}</p>
                </div>
            {/each}
        </div>
    </section>

    <!-- Timeline Section -->
    <section>
        <div class="text-center mb-12">
            <div
                class="inline-block mb-6 px-4 py-1 bg-secondary-100 dark:bg-secondary-900/30 rounded-full"
            >
                <span
                    class="text-secondary-600 dark:text-secondary-400 font-medium"
                    >Our Journey</span
                >
            </div>
            <h2 class="text-3xl font-bold text-surface-900-50">
                Building Success Over Time
            </h2>
        </div>
        <div class="relative">
            <!-- Timeline Line -->
            <div
                class="absolute left-1/2 top-0 bottom-0 w-0.5 bg-surface-200-700 transform -translate-x-1/2"
            ></div>

            {#each [{ year: "2015", title: "Company Founded", description: "Started as a small residential construction company", align: "left" }, { year: "2017", title: "Commercial Division Launch", description: "Expanded into commercial construction projects", align: "right" }, { year: "2020", title: "Safety Excellence Award", description: "Recognized for outstanding safety practices", align: "left" }, { year: "2023", title: "LEED Certification", description: "Became certified in sustainable construction", align: "right" }] as milestone, i}
                <div class="relative z-10 mb-12">
                    <div
                        class="flex items-center {milestone.align === 'left'
                            ? 'flex-row'
                            : 'flex-row-reverse'}"
                    >
                        <!-- Content -->
                        <div
                            class="w-1/2 px-6 {milestone.align === 'left'
                                ? 'text-right'
                                : 'text-left'}"
                        >
                            <div
                                class="bg-surface-50-900 p-6 rounded-xl shadow-sm inline-block max-w-md hover:shadow-md transition-shadow duration-300 border border-surface-200-700"
                            >
                                <span
                                    class="text-primary-500 font-bold text-xl mb-2 block"
                                    >{milestone.year}</span
                                >
                                <h3
                                    class="text-lg font-semibold text-surface-900-50 mb-2"
                                >
                                    {milestone.title}
                                </h3>
                                <p class="text-surface-700-200">
                                    {milestone.description}
                                </p>
                            </div>
                        </div>
                        <!-- Dot -->
                        <div
                            class="absolute left-1/2 transform -translate-x-1/2 flex items-center justify-center"
                        >
                            <div
                                class="w-4 h-4 rounded-full bg-primary-500 border-4 border-surface-50-900"
                            ></div>
                        </div>
                    </div>
                </div>
            {/each}
        </div>
    </section>
</div>
