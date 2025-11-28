<script setup lang="ts">
import { dashboard, login, register } from '@/routes';
import { Link } from '@inertiajs/vue3';
import icon from '@/images/reyes-logo.png';
import Icon from '@/components/Icon.vue';

</script>

<template>
    <footer class="container mx-auto w-full py-8 flex gap-x-12">
        <div class="flex flex-1 flex-col gap-4">
            <div>
                <img :src="icon" alt="Reyes Threads Logo" class="w-20">
            </div>
            <div class="flex gap-4">
                <a class="" href="">
                    <Icon class="w-6 h-6" name="Twitter" />
                </a>
                <a href="">
                    <Icon class="w-6 h-6" name="Instagram" />
                </a>
                <a href="">
                    <Icon class="w-6 h-6" name="Youtube" />
                </a>
            </div>
        </div>
        <div class="flex flex-2 justify-between">
            <ul class="space-y-2 flex-1">
                <li class="font-bold pb-2">Categories</li>
                <li><a href="">Semi-casual</a></li>
                <li><a href="">Seasonal</a></li>
                <li><a href="">Occasional</a></li>
                <li><a href="">New Arrivals</a></li>
                <li><a href="">Best Sellers</a></li>
            </ul>
            <ul class="space-y-2 flex-1">
                <li class="font-bold pb-2">Customer Support</li>
                <li><a href="">FAQs</a></li>
                <li><a href="">Shipping & Delivery Info</a></li>
                <li><a href="">Returns & Exchanges</a></li>
                <li><a href="">Order Tracking</a></li>
                <li><a href="">Size Guide</a></li>
                <li><a href="">Contact Us</a></li>
            </ul>
            <ul class="space-y-2 flex-1">
                <li class="font-bold pb-2">Legal & Policies</li>
                <li><a href="">Privacy Policy</a></li>
                <li><a href="">Terms & Conditions</a></li>
                <li><a href="">Cookie Policy</a></li>
                <li><a href="">Refund Policy</a></li>
                <li><a href="">Accessibility Statement</a></li>
            </ul>
        </div>
    </footer>
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
