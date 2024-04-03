<template>
    <div>
        <div class="absolute inset-0">
            <img src="/assets/images/auth/bg-gradient.png" alt="image" class="h-full w-full object-cover" />
        </div>
        <div
            class="relative flex min-h-screen items-center justify-center bg-[url(/assets/images/auth/map.png)] bg-cover bg-center bg-no-repeat px-6 py-10 dark:bg-[#060818] sm:px-16"
        >
            <img src="/assets/images/auth/coming-soon-object1.png" alt="image" class="absolute left-0 top-1/2 h-full max-h-[893px] -translate-y-1/2" />
            <img src="/assets/images/auth/coming-soon-object2.png" alt="image" class="absolute left-24 top-0 h-40 md:left-[30%]" />
            <img src="/assets/images/auth/coming-soon-object3.png" alt="image" class="absolute right-0 top-0 h-[300px]" />
            <img src="/assets/images/auth/polygon-object.svg" alt="image" class="absolute bottom-0 end-[28%]" />
            <div
                class="relative flex w-full max-w-[1502px] flex-col justify-between overflow-hidden rounded-md bg-white/60 text-center backdrop-blur-lg dark:bg-black/50 lg:min-h-[758px] lg:flex-row lg:gap-10 xl:gap-0"
            >
                <div
                    class="relative hidden w-full items-center justify-center p-5 lg:inline-flex lg:max-w-[835px] ltr:xl:-ml-24 ltr:xl:skew-x-[14deg] rtl:xl:-mr-24 rtl:xl:skew-x-[-14deg]"
                    style="background: linear-gradient(225deg, rgba(239, 18, 98, 1) 0%, rgba(67, 97, 238, 1) 100%)"
                >
                    <div
                        class="absolute inset-y-0 w-8 from-primary/10 via-transparent to-transparent ltr:-right-10 ltr:bg-gradient-to-r rtl:-left-10 rtl:bg-gradient-to-l xl:w-16 ltr:xl:-right-20 rtl:xl:-left-20"
                    ></div>
                    <div class="ltr:xl:-skew-x-[14deg] rtl:xl:skew-x-[14deg]">
                        <router-link to="/" class="w-48 block lg:w-72 mx-auto 2xl:m-0">
                            <img src="/assets/images/auth/logo-white.svg" alt="Logo" class="w-full" />
                        </router-link>
                        <div class="mt-24 hidden w-full max-w-[430px] rtl:rotate-y-180 lg:block">
                            <img src="/assets/images/auth/coming-soon-cover.svg" alt="Cover Image" class="w-full" />
                        </div>
                    </div>
                </div>
                <div class="relative w-full px-4 pb-16 pt-6 sm:px-6 lg:max-w-[667px]">
                    <div class="mx-auto mt-5 w-full max-w-[550px] lg:mt-16">
                        <router-link to="/" class="mb-8 block lg:hidden">
                            <img src="/assets/images/logo.svg" alt="Logo" class="mx-auto w-10" />
                        </router-link>
                        <div class="mb-12">
                            <h1 class="text-3xl font-extrabold uppercase !leading-snug text-primary md:text-4xl">Coming Soon</h1>
                            <p class="text-base font-bold leading-normal text-white-dark">We will be here in a shortwhile.....</p>
                        </div>
                        <div
                            class="mb-16 flex items-center justify-center gap-2 text-xl font-bold leading-none text-primary sm:text-2xl md:mb-24 md:gap-4 md:text-[50px]"
                        >
                            <div
                                class="relative inline-flex h-12 w-14 items-center justify-center rounded-md bg-primary-light p-2 sm:h-16 sm:w-16 md:h-24 md:min-w-[120px]"
                            >
                                <div class="absolute inset-1 flex flex-col gap-1">
                                    <span class="h-full w-full rounded-md bg-primary/[12%]"></span>
                                    <span class="h-full w-full rounded-md bg-white"></span>
                                </div>
                                <span class="relative">{{ demo1.days }}</span>
                            </div>
                            <span>:</span>
                            <div
                                class="relative inline-flex h-12 w-12 items-center justify-center rounded-md bg-primary-light p-2 sm:h-16 sm:w-16 md:h-24 md:min-w-[96px]"
                            >
                                <div class="absolute inset-1 flex flex-col gap-1">
                                    <span class="h-full w-full rounded-md bg-primary/[12%]"></span>
                                    <span class="h-full w-full rounded-md bg-white"></span>
                                </div>
                                <span class="relative">{{ demo1.hours }}</span>
                            </div>
                            <span>:</span>
                            <div
                                class="relative inline-flex h-12 w-12 items-center justify-center rounded-md bg-primary-light p-2 sm:h-16 sm:w-16 md:h-24 md:min-w-[96px]"
                            >
                                <div class="absolute inset-1 flex flex-col gap-1">
                                    <span class="h-full w-full rounded-md bg-primary/[12%]"></span>
                                    <span class="h-full w-full rounded-md bg-white"></span>
                                </div>
                                <span class="relative">{{ demo1.minutes }}</span>
                            </div>
                            <span>:</span>
                            <div
                                class="relative inline-flex h-12 w-12 items-center justify-center rounded-md bg-primary-light p-2 sm:h-16 sm:w-16 md:h-24 md:min-w-[96px]"
                            >
                                <div class="absolute inset-1 flex flex-col gap-1">
                                    <span class="h-full w-full rounded-md bg-primary/[12%]"></span>
                                    <span class="h-full w-full rounded-md bg-white"></span>
                                </div>
                                <span class="relative">{{ demo1.seconds }}</span>
                            </div>
                        </div>
                        <div class="mb-20 md:mb-32">
                            <h2 class="text-lg font-bold uppercase dark:text-white sm:text-xl">Subscribe to get notified!</h2>
                            <div class="relative mb-10 mt-8">
                                <input
                                    type="email"
                                    placeholder="mail@gmail.com"
                                    class="form-input mb-5 py-3.5 placeholder:text-base placeholder:text-white-dark sm:mb-0 sm:pe-32"
                                />
                                <button
                                    type="button"
                                    class="btn btn-gradient end-1.5 top-1/2 inline-flex border-0 px-4 py-1.5 text-base shadow-none sm:absolute sm:-translate-y-1/2"
                                    @click="router.push('/')"
                                >
                                    Subscribe
                                </button>
                            </div>
                            <ul class="flex justify-center gap-3.5 text-white">
                                <li>
                                    <a
                                        href="javascript:"
                                        class="inline-flex h-8 w-8 items-center justify-center rounded-full p-0 transition hover:scale-110"
                                        style="background: linear-gradient(135deg, rgba(239, 18, 98, 1) 0%, rgba(67, 97, 238, 1) 100%)"
                                    >
                                        <icon-instagram />
                                    </a>
                                </li>
                                <li>
                                    <a
                                        href="javascript:"
                                        class="inline-flex h-8 w-8 items-center justify-center rounded-full p-0 transition hover:scale-110"
                                        style="background: linear-gradient(135deg, rgba(239, 18, 98, 1) 0%, rgba(67, 97, 238, 1) 100%)"
                                    >
                                        <icon-facebook-circle />
                                    </a>
                                </li>
                                <li>
                                    <a
                                        href="javascript:"
                                        class="inline-flex h-8 w-8 items-center justify-center rounded-full p-0 transition hover:scale-110"
                                        style="background: linear-gradient(135deg, rgba(239, 18, 98, 1) 0%, rgba(67, 97, 238, 1) 100%)"
                                    >
                                        <icon-twitter :fill="true" />
                                    </a>
                                </li>
                                <li>
                                    <a
                                        href="javascript:"
                                        class="inline-flex h-8 w-8 items-center justify-center rounded-full p-0 transition hover:scale-110"
                                        style="background: linear-gradient(135deg, rgba(239, 18, 98, 1) 0%, rgba(67, 97, 238, 1) 100%)"
                                    >
                                        <icon-google />
                                    </a>
                                </li>
                            </ul>
                        </div>
                    </div>
                    <p class="absolute bottom-6 w-full text-center dark:text-white">© {{ new Date().getFullYear() }}.VRISTO All Rights Reserved.</p>
                </div>
            </div>
        </div>
    </div>
</template>
<script lang="ts" setup>
    import { ref, onMounted } from 'vue';
    import { useRouter } from 'vue-router';
    import { useMeta } from '@/composables/use-meta';

    import IconInstagram from '@/components/icon/icon-instagram.vue';
    import IconFacebookCircle from '@/components/icon/icon-facebook-circle.vue';
    import IconTwitter from '@/components/icon/icon-twitter.vue';
    import IconGoogle from '@/components/icon/icon-google.vue';

    useMeta({ title: 'Coming Soon Cover' });
    const router = useRouter();

    const timer1: any = ref(null);
    const demo1: any = ref({
        days: null,
        hours: null,
        minutes: null,
        seconds: null,
    });

    onMounted(() => {
        setTimerDemo1();
    });

    const setTimerDemo1 = () => {
        let date = new Date();
        date.setFullYear(date.getFullYear() + 1);
        let countDownDate = date.getTime();

        timer1.value = setInterval(() => {
            let now = new Date().getTime();

            let distance = countDownDate - now;

            demo1.value.days = Math.floor(distance / (1000 * 60 * 60 * 24));
            demo1.value.hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            demo1.value.minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            demo1.value.seconds = Math.floor((distance % (1000 * 60)) / 1000);

            if (distance < 0) {
                clearInterval(timer1.value);
            }
        }, 500);
    };
</script>
