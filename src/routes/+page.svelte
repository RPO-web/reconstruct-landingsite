<script lang="ts">
    import "../app.css";
    let { children } = $props();
    import ThemeSwitch from "$lib/components/ui/ThemeSwitch.svelte";
</script>

<div
    class="min-h-screen flex flex-col items-center justify-center bg-gradient-to-b from-primary-50 to-white p-6"
>
    <div><ThemeSwitch /></div>
    <div
        class="max-w-2xl w-full bg-white rounded-xl shadow-sm p-8 border border-primary-100"
    >
        <h1 class="text-3xl font-bold text-primary-900 mb-6 text-center">
            Welcome to your website demo
        </h1>

        <p class="text-lg text-primary-700 mb-8 text-center">
            Please choose which version of the website you'd like to visit. Both
            versions offer the same features, with a slight difference in how
            you can use contact forms.
        </p>

        <div class="space-y-6">
            <a
                href="/v1"
                class="block p-6 border border-primary-200 rounded-lg hover:border-primary-400 transition-all duration-300"
            >
                <h2 class="text-xl font-semibold text-primary-900 mb-2">
                    Version 1: Embedded form
                </h2>
                <p class="text-primary-600">
                    This version includes a contact form directly on the website
                    where you can type your message.
                    <br /><br />
                    - Form relies on external API: Free with limitations or $10 a
                    month for premium (you can start with free and upgrade later)
                </p>
            </a>

            <a
                href="/v2"
                class="block p-6 border border-primary-200 rounded-lg hover:border-primary-400 transition-all duration-300"
            >
                <h2 class="text-xl font-semibold text-primary-900 mb-2">
                    Version 2: External form
                </h2>
                <p class="text-primary-600">
                    This version uses a simple Google Form (or any other form
                    builder) for contact, which opens in a new window.
                    <br /><br />
                    - Completely free
                </p>
            </a>
        </div>

        <p class="mt-8 text-sm text-center text-primary-600"></p>
    </div>
</div>
