<script setup lang="ts">
import { Head } from '@inertiajs/vue3';
import Header from '@/components/Header.vue';
import Icon from '@/components/Icon.vue';
import Footer from '@/components/Footer.vue';

import heroImg from '@/images/hero-image.png';
import imgPlaceholder from '@/images/img-placeholder.png';

type FeaturedItem = {
    title: string;
    img: string;
};

const featured: FeaturedItem[] = [
    { title: "Premium Streetwear", img: imgPlaceholder },
    { title: "Limited Edition Drops", img: imgPlaceholder },
    { title: "Best-Selling Tees", img: imgPlaceholder },
    { title: "New Arrivals", img: imgPlaceholder }
];



type ProductItem = {
    name: string;
    desc: string;
    img: string;
    price: number;
};

const products: ProductItem[] = [
    { name: "Classic Hoodie", desc: "Comfortable cotton hoodie for everyday wear.", img: imgPlaceholder, price: 19.99 },
    { name: "Slim Fit Jeans", desc: "Stylish denim with a modern slim cut.", img: imgPlaceholder, price: 19.99 },
    { name: "Graphic Tee", desc: "Trendy t-shirt featuring unique designs.", img: imgPlaceholder, price: 19.99 },
    { name: "Leather Jacket", desc: "Premium leather jacket with a sleek look.", img: imgPlaceholder, price: 19.99 },
    { name: "Sneakers", desc: "Casual sneakers suitable for all occasions.", img: imgPlaceholder, price: 19.99 },
    { name: "Baseball Cap", desc: "Adjustable cap with embroidered logo.", img: imgPlaceholder, price: 19.99 },
    { name: "Sport Shorts", desc: "Lightweight shorts for sports or casual wear.", img: imgPlaceholder, price: 19.99 },
    { name: "Winter Scarf", desc: "Warm scarf made with soft fabric.", img: imgPlaceholder, price: 19.99 },
    { name: "Sunglasses", desc: "UV-protected stylish sunglasses.", img: imgPlaceholder, price: 19.99 },
    { name: "Backpack", desc: "Durable backpack for daily use.", img: imgPlaceholder, price: 19.99 },
    { name: "Wristwatch", desc: "Minimalist wristwatch with leather strap.", img: imgPlaceholder, price: 19.99 },
    { name: "Ankle Boots", desc: "Trendy ankle boots for casual or semi-formal wear.", img: imgPlaceholder, price: 19.99 },
];

type TestimonialItem = {
    name: string;
    email: string;
    profile_img: string;
    message: string;
}

const testimonials: TestimonialItem[] = [
  {
    name: "Alice Johnson",
    email: "alice.johnson@example.com",
    profile_img: "https://via.placeholder.com/150",
    message: "This service is amazing! Highly recommended."
  },
  {
    name: "Brian Smith",
    email: "brian.smith@example.com",
    profile_img: "https://via.placeholder.com/150",
    message: "A very professional and efficient team."
  },
  {
    name: "Catherine Lee",
    email: "catherine.lee@example.com",
    profile_img: "https://via.placeholder.com/150",
    message: "I loved the experience, everything was seamless."
  },
  {
    name: "David Kim",
    email: "david.kim@example.com",
    profile_img: "https://via.placeholder.com/150",
    message: "Exceptional quality and fantastic support."
  },
  {
    name: "Emily Davis",
    email: "emily.davis@example.com",
    profile_img: "https://via.placeholder.com/150",
    message: "I will definitely use this service again!"
  }
];


</script>

<template>
    <Head title="Homepage">
        <link rel="preconnect" href="https://rsms.me/" />
        <link rel="stylesheet" href="https://rsms.me/inter/inter.css" />
    </Head>

    <Header :can-register="true" />
    <section id="home" class="bg-[var(--primary-color)] h-[calc(100vh-101px)] overflow-hidden relative">
        <div class="container mx-auto w-full h-full flex">
            <div class="flex-1 flex flex-col gap-y-8 justify-center">
                <div>
                    <h1 class="text-7xl font-bold pb-2">
                        Where grace meets comfort
                    </h1>
                    <p class="text-4xl text-[var(--neutral-gray)]">
                        Effortless style without <br /> compromise
                    </p>
                </div>
                <div>
                    <button class="flex items-center gap-x-1 text-4xl rounded-lg p-4 text-[var(--secondary-color)] 
                        border-2 border-[var(--secondary-color)] hover:bg-[var(--secondary-color)] hover:text-white
                        transition-all cursor-pointer"
                    >
                        Learn More
                        <Icon name="ArrowRight" class="h-8 w-8"/>
                    </button>
                </div>
            </div>
            <div class="flex-1">
                <img :src="heroImg" alt="Fashion Clothing Image" class="absolute w-1/2 h-full top-0 right-0 bottom-0 object-cover">
            </div>
        </div>
    </section>
    <section id="features" class="bg-[var(--secondary-color)] pt-1 pb-4">
        <h2 class="text-center text-3xl py-2 text-white">Featured Brands</h2>
        <div class="flex gap-x-2">
            <div v-for="(brand, id) in featured" :key="id" class="flex-1 overflow-hidden rounded-2xl h-48">
                <img :src="brand.img" :alt=brand.title class="w-full h-full object-cover" />
            </div>
        </div>
    </section>
    <section id="shop" class="min-h-[100vh] container mx-auto w-full py-4">
        <div class="py-4 text-xl">
            <button class="active px-6 cursor-pointer border-b-2 border-[var(--neutral-gray)]/50 hover:border-[var(--neutral-dark-gray)] transition-all">
                New Arrivals
            </button>
            <button class="px-6 cursor-pointer border-b-2 border-[var(--neutral-gray)]/50 hover:border-[var(--neutral-dark-gray)] transition-all">
                Best Sellers
            </button>
        </div>
        <div class="grid md:grid-cols-4 gap-4">
            <div class="h-120" v-for="product, id in products" :key="id">
                <div>
                    <img :src="product.img" :alt="product.desc" class="w-full h-full">
                </div>
                <div class="flex justify-between items-center py-2 gap-x-8">
                    <div>
                        <h3 class="text-xl">
                            {{ product.name }}
                        </h3>
                        <p class="text-sm leading-tight text-[var(--neutral-gray)]">
                            {{ product.desc }}
                        </p>
                    </div>
                    <div>
                        <p> P{{ product.price }} </p>
                    </div>
                </div>
            </div>
        </div>
    </section>
    <section id="contact" class="bg-[var(--primary-color)] py-16 flex justify-center items-center">
        <div class="container mx-auto w-full">
            <div class="text-center pb-8">
                <p>Our Beloved</p>
                <h3 class="text-3xl">
                    Customer's Feedback
                </h3>
            </div>
            <div class="flex flex-wrap gap-5 items-center justify-center">
                <div
                    v-for="testimony in testimonials"
                    class="w-72 min-w-72 p-6 bg-white rounded-lg border-2 border-gray-200 inline-flex flex-col justify-start items-start gap-6"
                >
                    <div class="self-stretch inline-flex justify-start items-start">
                        <div class="flex-1 justify-start text-Neutral text-2xl font-semibold leading-7">Lorem ipsum cursus ultrices a hendrerit nulla.</div>
                    </div>
                    <div class="self-stretch inline-flex justify-start items-center gap-3">
                        <div data-shape="Circle" data-size="Large" data-type="Image" class="w-10 h-10 relative rounded-full overflow-hidden">
                            <img class="w-10 h-10 left-0 top-0 absolute" src="https://placehold.co/40x40" />
                        </div>
                        <div class="inline-flex flex-col justify-start items-start gap-0.5">
                        <div class="self-stretch justify-center text-Text-Default-Secondary text-base font-semibold font-['Podkova'] leading-6">Franchesca</div>
                        <div class="self-stretch justify-center text-Text-Default-Tertiary text-base font-normal font-['Podkova'] leading-6">franchesca@gmail.com</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    <Footer />
</template>

<style lang="css" scoped>
    #shop button.active {
        border-bottom: 2px var(--neutral-dark-gray) solid;
    }
</style>
