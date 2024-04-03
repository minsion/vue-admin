<template>
    <div>
        <div
            class="fixed inset-0 bg-[black]/60 z-[51] px-4 hidden transition-[display]"
            :class="{ '!block': showCustomizer }"
            @click="showCustomizer = false"
        ></div>

        <nav
            class="bg-white fixed ltr:-right-[400px] rtl:-left-[400px] top-0 bottom-0 w-full max-w-[400px] shadow-[5px_0_25px_0_rgba(94,92,154,0.1)] transition-[right] duration-300 z-[51] dark:bg-[#0e1726] p-4"
            :class="{ 'ltr:!right-0 rtl:!left-0': showCustomizer }"
        >
            <a
                href="javascript:;"
                class="bg-primary ltr:rounded-tl-full rtl:rounded-tr-full ltr:rounded-bl-full rtl:rounded-br-full absolute ltr:-left-12 rtl:-right-12 top-0 bottom-0 my-auto w-12 h-10 flex justify-center items-center text-white cursor-pointer"
                @click="showCustomizer = !showCustomizer"
            >
                <icon-settings class="animate-[spin_3s_linear_infinite] w-5 h-5" />
            </a>
            <perfect-scrollbar
                :options="{
                    swipeEasing: true,
                    wheelPropagation: false,
                }"
                class="relative h-full overflow-x-hidden ltr:pr-3 rtl:pl-3 ltr:-mr-3 rtl:-ml-3"
            >
                <div>
                    <div class="text-center relative pb-5">
                        <a
                            href="javascript:;"
                            class="absolute top-0 ltr:right-0 rtl:left-0 opacity-30 hover:opacity-100 dark:text-white"
                            @click="showCustomizer = false"
                        >
                            <icon-x class="w-5 h-5" />
                        </a>
                        <h4 class="mb-1 dark:text-white">TEMPLATE CUSTOMIZER</h4>
                        <p class="text-white-dark">Set preferences that will be cookied for your live preview demonstration.</p>
                    </div>
                    <div class="border border-dashed border-[#e0e6ed] dark:border-[#1b2e4b] rounded-md mb-3 p-3">
                        <h5 class="mb-1 text-base dark:text-white leading-none">Color Scheme</h5>
                        <p class="text-white-dark text-xs">Overall light or dark presentation.</p>
                        <div class="grid grid-cols-3 gap-2 mt-3">
                            <button
                                type="button"
                                class="btn"
                                :class="[store.theme === 'light' ? 'btn-primary' : 'btn-outline-primary']"
                                @click="store.toggleTheme('light')"
                            >
                                <icon-sun class="w-5 h-5 shrink-0 ltr:mr-2 rtl:ml-2" />
                                Light
                            </button>
                            <button
                                type="button"
                                class="btn"
                                :class="[store.theme === 'dark' ? 'btn-primary' : 'btn-outline-primary']"
                                @click="store.toggleTheme('dark')"
                            >
                                <icon-moon class="w-5 h-5 shrink-0 ltr:mr-2 rtl:ml-2" />
                                Dark
                            </button>
                            <button
                                type="button"
                                class="btn"
                                :class="[store.theme === 'system' ? 'btn-primary' : 'btn-outline-primary']"
                                @click="store.toggleTheme('system')"
                            >
                                <icon-laptop class="w-5 h-5 shrink-0 ltr:mr-2 rtl:ml-2" />
                                System
                            </button>
                        </div>
                    </div>

                    <div class="border border-dashed border-[#e0e6ed] dark:border-[#1b2e4b] rounded-md mb-3 p-3">
                        <h5 class="mb-1 text-base dark:text-white leading-none">Navigation Position</h5>
                        <p class="text-white-dark text-xs">Select the primary navigation paradigm for your app.</p>
                        <div class="grid grid-cols-3 gap-2 mt-3">
                            <button
                                type="button"
                                class="btn"
                                :class="[store.menu === 'horizontal' ? 'btn-primary' : 'btn-outline-primary']"
                                @click="store.toggleMenu('horizontal')"
                            >
                                Horizontal
                            </button>
                            <button
                                type="button"
                                class="btn"
                                :class="[store.menu === 'vertical' ? 'btn-primary' : 'btn-outline-primary']"
                                @click="store.toggleMenu('vertical')"
                            >
                                Vertical
                            </button>
                            <button
                                type="button"
                                class="btn"
                                :class="[store.menu === 'collapsible-vertical' ? 'btn-primary' : 'btn-outline-primary']"
                                @click="store.toggleMenu('collapsible-vertical')"
                            >
                                Collapsible
                            </button>
                        </div>
                        <div class="mt-5 text-primary">
                            <label class="inline-flex mb-0">
                                <input v-model="store.semidark" type="checkbox" class="form-checkbox" @change="store.toggleSemidark(store.semidark)" />
                                <span>Semi Dark (Sidebar & Header)</span>
                            </label>
                        </div>
                    </div>
                    <div class="border border-dashed border-[#e0e6ed] dark:border-[#1b2e4b] rounded-md mb-3 p-3">
                        <h5 class="mb-1 text-base dark:text-white leading-none">Layout Style</h5>
                        <p class="text-white-dark text-xs">Select the primary layout style for your app.</p>
                        <div class="flex gap-2 mt-3">
                            <button
                                type="button"
                                class="btn flex-auto"
                                :class="[store.layout === 'boxed-layout' ? 'btn-primary' : 'btn-outline-primary']"
                                @click="store.toggleLayout('boxed-layout')"
                            >
                                Box
                            </button>
                            <button
                                type="button"
                                class="btn flex-auto"
                                :class="[store.layout === 'full' ? 'btn-primary' : 'btn-outline-primary']"
                                @click="store.toggleLayout('full')"
                            >
                                Full
                            </button>
                        </div>
                    </div>
                    <div class="border border-dashed border-[#e0e6ed] dark:border-[#1b2e4b] rounded-md mb-3 p-3">
                        <h5 class="mb-1 text-base dark:text-white leading-none">Direction</h5>
                        <p class="text-white-dark text-xs">Select the direction for your app.</p>
                        <div class="flex gap-2 mt-3">
                            <button
                                type="button"
                                class="btn flex-auto"
                                :class="[store.rtlClass === 'ltr' ? 'btn-primary' : 'btn-outline-primary']"
                                @click="store.toggleRTL('ltr')"
                            >
                                LTR
                            </button>
                            <button
                                type="button"
                                class="btn flex-auto"
                                :class="[store.rtlClass === 'rtl' ? 'btn-primary' : 'btn-outline-primary']"
                                @click="store.toggleRTL('rtl')"
                            >
                                RTL
                            </button>
                        </div>
                    </div>

                    <div class="border border-dashed border-[#e0e6ed] dark:border-[#1b2e4b] rounded-md mb-3 p-3">
                        <h5 class="mb-1 text-base dark:text-white leading-none">Navbar Type</h5>
                        <p class="text-white-dark text-xs">Sticky or Floating.</p>
                        <div class="mt-3 flex items-center gap-3 text-primary">
                            <label class="inline-flex mb-0">
                                <input
                                    :checked="store.navbar === 'navbar-sticky'"
                                    type="radio"
                                    value="navbar-sticky"
                                    class="form-radio"
                                    @change="store.toggleNavbar('navbar-sticky')"
                                />
                                <span>Sticky</span>
                            </label>
                            <label class="inline-flex mb-0">
                                <input
                                    :checked="store.navbar === 'navbar-floating'"
                                    type="radio"
                                    value="navbar-floating"
                                    class="form-radio"
                                    @change="store.toggleNavbar('navbar-floating')"
                                />
                                <span>Floating</span>
                            </label>
                            <label class="inline-flex mb-0">
                                <input
                                    :checked="store.navbar === 'navbar-static'"
                                    type="radio"
                                    value="navbar-static"
                                    class="form-radio"
                                    @change="store.toggleNavbar('navbar-static')"
                                />
                                <span>Static</span>
                            </label>
                        </div>
                    </div>

                    <div class="border border-dashed border-[#e0e6ed] dark:border-[#1b2e4b] rounded-md mb-3 p-3">
                        <h5 class="mb-1 text-base dark:text-white leading-none">Router Transition</h5>
                        <p class="text-white-dark text-xs">Animation of main content.</p>
                        <div class="mt-3">
                            <select v-model="store.animation" class="form-select border-primary text-primary" @change="store.toggleAnimation()">
                                <option value="">None</option>
                                <option value="animate__fadeIn">Fade</option>
                                <option value="animate__fadeInDown">Fade Down</option>
                                <option value="animate__fadeInUp">Fade Up</option>
                                <option value="animate__fadeInLeft">Fade Left</option>
                                <option value="animate__fadeInRight">Fade Right</option>
                                <option value="animate__slideInDown">Slide Down</option>
                                <option value="animate__slideInLeft">Slide Left</option>
                                <option value="animate__slideInRight">Slide Right</option>
                                <option value="animate__zoomIn">Zoom In</option>
                            </select>
                        </div>
                    </div>
                </div>
            </perfect-scrollbar>
        </nav>
    </div>
</template>

<script lang="ts" setup>
    import { ref } from 'vue';
    import { useAppStore } from '@/stores/index';
    import IconSettings from '@/components/icon/icon-settings.vue';
    import IconX from '@/components/icon/icon-x.vue';
    import IconSun from '@/components/icon/icon-sun.vue';
    import IconMoon from '@/components/icon/icon-moon.vue';
    import IconLaptop from '@/components/icon/icon-laptop.vue';
    const store = useAppStore();
    const showCustomizer = ref(false);
</script>
