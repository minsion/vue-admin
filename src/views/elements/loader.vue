<template>
    <div>
        <ul class="flex space-x-2 rtl:space-x-reverse">
            <li>
                <a href="javascript:;" class="text-primary hover:underline">Elements</a>
            </li>
            <li class="before:content-['/'] ltr:before:mr-2 rtl:before:ml-2">
                <span>Loader</span>
            </li>
        </ul>
        <div class="pt-5 grid grid-cols-1 lg:grid-cols-2 gap-6">
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Loaders with Buttons</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code1')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span></a
                    >
                </div>
                <div class="mb-5">
                    <div class="flex flex-wrap items-center justify-center w-full gap-4">
                        <button type="button" class="btn btn-info btn-lg">
                            <icon-loader class="animate-[spin_2s_linear_infinite] inline-block align-middle ltr:mr-2 rtl:ml-2 shrink-0" />
                            Loading
                        </button>

                        <button type="button" class="btn btn-danger btn-lg">
                            <span
                                class="animate-spin border-2 border-white border-l-transparent rounded-full w-5 h-5 ltr:mr-4 rtl:ml-4 inline-block align-middle shrink-0"
                            ></span
                            >Loading
                        </button>

                        <button type="button" class="btn btn-secondary btn-lg">
                            <span class="animate-ping w-3 h-3 ltr:mr-4 rtl:ml-4 inline-block rounded-full bg-white shrink-0"></span>
                            Loading
                        </button>
                    </div>
                </div>
                <template v-if="codeArr.includes('code1')">
                    <highlight>
                        <pre>
&lt;!-- info --&gt;
&lt;button type=&quot;button&quot; class=&quot;btn btn-info btn-lg&quot;&gt;
  &lt;svg&gt; ... &lt;/svg&gt;
  Loading
&lt;/button&gt;

&lt;button type=&quot;button&quot; class=&quot;btn btn-danger btn-lg&quot;&gt;
  &lt;span class=&quot;animate-spin border-2 border-white border-l-transparent rounded-full w-5 h-5 ltr:mr-4 rtl:ml-4 inline-block align-middle&quot;&gt;&lt;/span&gt;Loading
&lt;/button&gt;

&lt;button type=&quot;button&quot; class=&quot;btn btn-secondary btn-lg&quot;&gt;
  &lt;span class=&quot;animate-ping w-3 h-3 ltr:mr-4 rtl:ml-4 inline-block rounded-full bg-white&quot;&gt;&lt;/span&gt;
  Loading
&lt;/button&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Position</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code2')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span></a
                    >
                </div>
                <div class="mb-5">
                    <div class="flex flex-wrap w-full">
                        <div class="flex flex-wrap items-center justify-center w-full sm:w-1/2 text-center mb-3 sm:mb-0">
                            <p class="w-full mb-2">Default Button</p>
                            <button type="button" class="btn btn-primary btn-lg">
                                <icon-loader class="animate-[spin_2s_linear_infinite] inline-block align-middle ltr:mr-2 rtl:ml-2 shrink-0" />
                                Loading
                            </button>
                        </div>
                        <div class="flex flex-wrap items-center justify-center w-full sm:w-1/2 text-center">
                            <p class="w-full mb-2">Outline Button</p>
                            <button type="button" class="btn btn-outline-primary btn-lg">
                                Loading
                                <icon-loader class="animate-[spin_2s_linear_infinite] inline-block align-middle ltr:ml-2 rtl:mr-2 shrink-0" />
                            </button>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code2')">
                    <highlight>
                        <pre>
&lt;!-- default --&gt;
&lt;div class=&quot;flex flex-wrap items-center justify-center w-full sm:w-1/2 text-center mb-3 sm:mb-0&quot;&gt;
  &lt;p class=&quot;w-full mb-2&quot;&gt;Default Button&lt;/p&gt;
  &lt;button type=&quot;button&quot; class=&quot;btn btn-primary btn-lg&quot;&gt;
    &lt;svg&gt; ... &lt;/svg&gt;
    Loading
  &lt;/button&gt;
&lt;/div&gt;

&lt;!-- outline --&gt;
&lt;div class=&quot;flex flex-wrap items-center justify-center w-full sm:w-1/2 text-center&quot;&gt;
  &lt;p class=&quot;w-full mb-2&quot;&gt;Outline Button&lt;/p&gt;
  &lt;button type=&quot;button&quot; class=&quot;btn btn-outline-primary btn-lg&quot;&gt;
    Loading
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/button&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <div class="panel">
                <div class="flex items-center justify-between mb-10">
                    <h5 class="font-semibold text-lg dark:text-white-light">Sizes</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code3')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span></a
                    >
                </div>
                <div class="mb-5">
                    <div class="grid grid-cols-3 w-full gap-4">
                        <span
                            class="animate-spin border-4 border-success border-l-transparent rounded-full w-12 h-12 inline-block align-middle m-auto mb-10"
                        ></span>
                        <span
                            class="animate-spin border-4 border-success border-l-transparent rounded-full w-10 h-10 inline-block align-middle m-auto mb-10"
                        ></span>
                        <span
                            class="animate-spin border-[3px] border-success border-l-transparent rounded-full w-6 h-6 inline-block align-middle m-auto mb-10"
                        ></span>
                        <span
                            class="animate-spin border-4 border-transparent border-l-primary rounded-full w-12 h-12 inline-block align-middle m-auto mb-10"
                        ></span>
                        <span
                            class="animate-spin border-4 border-transparent border-l-primary rounded-full w-10 h-10 inline-block align-middle m-auto mb-10"
                        ></span>
                        <span
                            class="animate-spin border-[3px] border-transparent border-l-primary rounded-full w-6 h-6 inline-block align-middle m-auto mb-10"
                        ></span>
                        <span class="w-5 h-5 m-auto mb-10"><span class="animate-ping inline-flex h-full w-full rounded-full bg-info"></span></span>
                        <span class="w-4 h-4 m-auto mb-10"><span class="animate-ping inline-flex h-full w-full rounded-full bg-info"></span></span>
                        <span class="w-3 h-3 m-auto mb-10"><span class="animate-ping inline-flex h-full w-full rounded-full bg-info"></span></span>
                    </div>
                </div>
                <template v-if="codeArr.includes('code3')">
                    <highlight>
                        <pre>
&lt;!-- large --&gt;
&lt;span class=&quot;animate-spin border-4 border-success border-l-transparent rounded-full w-12 h-12 inline-block align-middle m-auto mb-10&quot;&gt;&lt;/span&gt;

&lt;!-- default --&gt;
&lt;span class=&quot;animate-spin border-4 border-success border-l-transparent rounded-full w-10 h-10 inline-block align-middle m-auto mb-10&quot;&gt;&lt;/span&gt;

&lt;!-- small --&gt;
&lt;span class=&quot;animate-spin border-[3px] border-success border-l-transparent rounded-full w-6 h-6 inline-block align-middle m-auto mb-10&quot;&gt;&lt;/span&gt;

&lt;!-- large --&gt;
&lt;span class=&quot;animate-spin border-4 border-transparent border-l-primary rounded-full w-12 h-12 inline-block align-middle m-auto mb-10&quot;&gt;&lt;/span&gt;

&lt;!-- default --&gt;
&lt;span class=&quot;animate-spin border-4 border-transparent border-l-primary rounded-full w-10 h-10 inline-block align-middle m-auto mb-10&quot;&gt;&lt;/span&gt;

&lt;!-- small --&gt;
&lt;span class=&quot;animate-spin border-[3px] border-transparent border-l-primary rounded-full w-6 h-6 inline-block align-middle m-auto mb-10&quot;&gt;&lt;/span&gt;

&lt;!-- large --&gt;
&lt;span class=&quot;w-5 h-5 m-auto mb-10&quot;&gt;&lt;span class=&quot;animate-ping inline-flex h-full w-full rounded-full bg-info&quot;&gt;&lt;/span&gt;&lt;/span&gt;

&lt;!-- default --&gt;
&lt;span class=&quot;w-4 h-4 m-auto mb-10&quot;&gt;&lt;span class=&quot;animate-ping inline-flex h-full w-full rounded-full bg-info&quot;&gt;&lt;/span&gt;&lt;/span&gt;

&lt;!-- small --&gt;
&lt;span class=&quot;w-3 h-3 m-auto mb-10&quot;&gt;&lt;span class=&quot;animate-ping inline-flex h-full w-full rounded-full bg-info&quot;&gt;&lt;/span&gt;&lt;/span&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <div class="panel">
                <div class="flex items-center justify-between mb-10">
                    <h5 class="font-semibold text-lg dark:text-white-light">Colors</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code4')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span></a
                    >
                </div>
                <div class="mb-5">
                    <div class="grid grid-cols-4 w-full gap-4">
                        <span
                            class="animate-spin border-4 border-success border-l-transparent rounded-full w-10 h-10 inline-block align-middle m-auto mb-10"
                        ></span>
                        <span
                            class="animate-spin border-4 border-danger border-l-transparent rounded-full w-10 h-10 inline-block align-middle m-auto mb-10"
                        ></span>
                        <span
                            class="animate-spin border-4 border-warning border-l-transparent rounded-full w-10 h-10 inline-block align-middle m-auto mb-10"
                        ></span>
                        <span
                            class="animate-spin border-4 border-primary border-l-transparent rounded-full w-10 h-10 inline-block align-middle m-auto mb-10"
                        ></span>
                        <span
                            class="animate-spin border-4 border-transparent border-l-black rounded-full w-10 h-10 inline-block align-middle m-auto mb-10 dark:border-l-dark"
                        ></span>
                        <span
                            class="animate-spin border-4 border-transparent border-l-danger rounded-full w-10 h-10 inline-block align-middle m-auto mb-10"
                        ></span>
                        <span
                            class="animate-spin border-4 border-transparent border-l-warning rounded-full w-10 h-10 inline-block align-middle m-auto mb-10"
                        ></span>
                        <span
                            class="animate-spin border-4 border-transparent border-l-primary rounded-full w-10 h-10 inline-block align-middle m-auto mb-10"
                        ></span>
                        <span class="w-4 h-4 m-auto mb-10"><span class="animate-ping inline-flex h-full w-full rounded-full bg-info"></span></span>
                        <span class="w-4 h-4 m-auto mb-10"><span class="animate-ping inline-flex h-full w-full rounded-full bg-danger"></span></span>
                        <span class="w-4 h-4 m-auto mb-10"><span class="animate-ping inline-flex h-full w-full rounded-full bg-warning"></span></span>
                        <span class="w-4 h-4 m-auto mb-10"><span class="animate-ping inline-flex h-full w-full rounded-full bg-primary"></span></span>
                    </div>
                </div>
                <template v-if="codeArr.includes('code4')">
                    <highlight>
                        <pre>
&lt;!-- success --&gt;
&lt;span class=&quot;animate-spin border-4 border-success border-l-transparent rounded-full w-10 h-10 inline-block align-middle m-auto mb-10&quot;&gt;&lt;/span&gt;

&lt;!-- danger --&gt;
&lt;span class=&quot;animate-spin border-4 border-danger border-l-transparent rounded-full w-10 h-10 inline-block align-middle m-auto mb-10&quot;&gt;&lt;/span&gt;

&lt;!-- warning --&gt;
&lt;span class=&quot;animate-spin border-4 border-warning border-l-transparent rounded-full w-10 h-10 inline-block align-middle m-auto mb-10&quot;&gt;&lt;/span&gt;

&lt;!-- primary --&gt;
&lt;span class=&quot;animate-spin border-4 border-primary border-l-transparent rounded-full w-10 h-10 inline-block align-middle m-auto mb-10&quot;&gt;&lt;/span&gt;

&lt;!-- black --&gt;
&lt;span class=&quot;animate-spin border-4 border-transparent border-l-black rounded-full w-10 h-10 inline-block align-middle m-auto mb-10 dark:border-l-dark&quot;&gt;&lt;/span&gt;

&lt;!-- danger --&gt;
&lt;span class=&quot;animate-spin border-4 border-transparent border-l-danger rounded-full w-10 h-10 inline-block align-middle m-auto mb-10&quot;&gt;&lt;/span&gt;

&lt;!-- warning --&gt;
&lt;span class=&quot;animate-spin border-4 border-transparent border-l-warning rounded-full w-10 h-10 inline-block align-middle m-auto mb-10&quot;&gt;&lt;/span&gt;

&lt;!-- primary --&gt;
&lt;span class=&quot;animate-spin border-4 border-transparent border-l-primary rounded-full w-10 h-10 inline-block align-middle m-auto mb-10&quot;&gt;&lt;/span&gt;

&lt;!-- info --&gt;
&lt;span class=&quot;w-4 h-4 m-auto mb-10&quot;&gt;&lt;span class=&quot;animate-ping inline-flex h-full w-full rounded-full bg-info&quot;&gt;&lt;/span&gt;&lt;/span&gt;

&lt;!-- danger --&gt;
&lt;span class=&quot;w-4 h-4 m-auto mb-10&quot;&gt;&lt;span class=&quot;animate-ping inline-flex h-full w-full rounded-full bg-danger&quot;&gt;&lt;/span&gt;&lt;/span&gt;

&lt;!-- warning --&gt;
&lt;span class=&quot;w-4 h-4 m-auto mb-10&quot;&gt;&lt;span class=&quot;animate-ping inline-flex h-full w-full rounded-full bg-warning&quot;&gt;&lt;/span&gt;&lt;/span&gt;

&lt;!-- primary --&gt;
&lt;span class=&quot;w-4 h-4 m-auto mb-10&quot;&gt;&lt;span class=&quot;animate-ping inline-flex h-full w-full rounded-full bg-primary&quot;&gt;&lt;/span&gt;&lt;/span&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <div class="panel">
                <div class="flex items-center justify-between mb-10">
                    <h5 class="font-semibold text-lg dark:text-white-light">Custom</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code5')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5">
                    <div class="grid grid-cols-3 w-full gap-4">
                        <span
                            class="animate-spin border-8 border-[#f1f2f3] border-l-primary rounded-full w-14 h-14 inline-block align-middle m-auto mb-10"
                        ></span>
                        <span
                            class="animate-[spin_2s_linear_infinite] border-8 border-[#f1f2f3] border-l-primary border-r-primary rounded-full w-14 h-14 inline-block align-middle m-auto mb-10"
                        ></span>
                        <span
                            class="animate-[spin_3s_linear_infinite] border-8 border-r-warning border-l-primary border-t-danger border-b-success rounded-full w-14 h-14 inline-block align-middle m-auto mb-10"
                        ></span>
                    </div>
                </div>
                <template v-if="codeArr.includes('code5')">
                    <highlight>
                        <pre>
&lt;!-- custom loader --&gt;
&lt;span class=&quot;animate-spin border-8 border-[#f1f2f3] border-l-primary rounded-full w-14 h-14 inline-block align-middle m-auto mb-10&quot;&gt;&lt;/span&gt;

&lt;!-- custom loader --&gt
&lt;span class=&quot;animate-[spin_2s_linear_infinite] border-8 border-[#f1f2f3] border-l-primary border-r-primary rounded-full w-14 h-14 inline-block align-middle m-auto mb-10&quot;&gt;&lt;/span&gt;

&lt;!-- custom loader --&gt
&lt;span
  class=&quot;animate-[spin_3s_linear_infinite] border-8 border-r-warning border-l-primary border-t-danger border-b-success rounded-full w-14 h-14 inline-block align-middle m-auto mb-10&quot;
&gt;&lt;/span&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
        </div>
    </div>
</template>
<script lang="ts" setup>
    import highlight from '@/components/plugins/highlight.vue';
    import codePreview from '@/composables/codePreview';
    import { useMeta } from '@/composables/use-meta';

    import IconCode from '@/components/icon/icon-code.vue';
    import IconLoader from '@/components/icon/icon-loader.vue';

    useMeta({ title: 'Loader' });

    const { codeArr, toggleCode } = codePreview();
</script>
