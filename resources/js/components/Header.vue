<script setup lang="ts">
import { dashboard, login, register } from '@/routes';
import { Link } from '@inertiajs/vue3';
import icon from '@/images/reyes-logo.png';

withDefaults(
    defineProps<{
        canRegister: boolean;
    }>(),
    {
        canRegister: true,
    },
);
</script>

<template>
    <header
        class="py-4 container mx-auto w-full text-lg not-has-[nav]:hidden"
    >
        <nav class="flex items-center justify-between gap-4">
            <div>
                <img :src="icon" alt="Reyes Threads Logo" class="w-20">
            </div>
            <div class="flex-1 flex justify-end gap-x-2">
                <div class="px-1"><a href="#home" class="nav-btn">Home</a></div>
                <div class="px-1"><a href="#features" class="nav-btn">Features</a></div>
                <div class="px-1"><a href="#shop" class="nav-btn">Shop</a></div>
                <div class="px-1"><a href="#contact" class="nav-btn">Contact</a></div>
            </div>
            <div class="flex gap-x-1">
                <Link
                    v-if="$page.props.auth.user"
                    :href="dashboard()"
                    class="inline-block rounded-lg border border-[#19140035] px-5 py-1.5 leading-normal text-[#1b1b18] hover:border-[#1915014a] dark:border-[#3E3E3A] dark:text-[#EDEDEC] dark:hover:border-[#62605b]"
                >
                    Dashboard
                </Link>
                <template v-else>
                    <Link
                        :href="login()"
                        class="inline-block rounded-lg border border-[var(--secondary-color)] px-5 py-1.5 leading-normal text-[#1b1b18] hover:text-white hover:bg-[var(--secondary-color)] transition-all dark:text-[#EDEDEC] dark:hover:border-[#3E3E3A]"
                    >
                        Sign in
                    </Link>
                    <Link
                        v-if="canRegister"
                        :href="register()"
                        class="inline-block rounded-lg border border-transparent bg-black/80 text-white px-5 py-1.5 leading-normal hover:bg-black/70 dark:border-[#3E3E3A] dark:text-[#EDEDEC] dark:hover:border-[#62605b]"
                    >
                        Register
                    </Link>
                </template>
            </div>
        </nav>
    </header>
</template>

<style lang="css" scoped>
    .nav-btn {
        border-bottom: 4px transparent solid;
        transition: all 0.25s ease;
    }

    .nav-btn:hover {
        border-bottom: 4px var(--secondary-color) solid;
    }
</style>
