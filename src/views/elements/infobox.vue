<template>
    <div>
        <ul class="flex space-x-2 rtl:space-x-reverse">
            <li>
                <a href="javascript:;" class="text-primary hover:underline">Elements</a>
            </li>
            <li class="before:content-['/'] ltr:before:mr-2 rtl:before:ml-2">
                <span>Infobox</span>
            </li>
        </ul>
        <div class="pt-5 grid grid-cols-1 lg:grid-cols-2 gap-6">
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Infobox 1</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code1')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span></a
                    >
                </div>
                <div class="mb-5">
                    <div class="flex flex-wrap w-full justify-center">
                        <div
                            class="border border-gray-500/20 rounded-md shadow-[rgb(31_45_61_/_10%)_0px_2px_10px_1px] dark:shadow-[0_2px_11px_0_rgb(6_8_24_/_39%)] p-6"
                        >
                            <div class="text-primary mb-5">
                                <icon-box class="w-12 h-12" />
                            </div>
                            <h5 class="text-lg font-semibold mb-3.5 dark:text-white-light">Layout Package</h5>
                            <p class="text-white-dark text-[15px] mb-3.5">Lorem ipsum dolor sit amet, labore et dolore magna aliqua.</p>
                            <a href="javascript:;" class="text-primary font-semibold hover:underline group"
                                >Discover
                                <icon-arrow-left
                                    class="ltr:ml-1 rtl:mr-1 inline-block relative transition-all duration-300 group-hover:translate-x-2 rtl:group-hover:-translate-x-2 rtl:rotate-180"
                                />
                            </a>
                        </div>
                    </div>
                </div>

                <template v-if="codeArr.includes('code1')">
                    <highlight>
                        <pre>
&lt;!-- infobox --&gt;
&lt;div class=&quot;flex flex-wrap w-full justify-center&quot;&gt;
  &lt;div class=&quot;border border-gray-500/20 rounded-md shadow-[rgb(31_45_61_/_10%)_0px_2px_10px_1px] dark:shadow-[0_2px_11px_0_rgb(6_8_24_/_39%)] p-6&quot;&gt;
    &lt;div class=&quot;text-primary mb-5&quot;&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/div&gt;
    &lt;h5 class=&quot;text-lg font-semibold mb-3.5 dark:text-white-light&quot;&gt;Layout Package&lt;/h5&gt;
    &lt;p class=&quot;text-white-dark text-[15px] mb-3.5&quot;&gt;Lorem ipsum dolor sit amet, labore et dolore magna aliqua.&lt;/p&gt;
    &lt;a href=&quot;javascript:;&quot; class=&quot;text-primary font-semibold hover:underline group&quot;
      &gt;Discover
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/a&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Infobox 2</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code2')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span></a
                    >
                </div>
                <div class="mb-5">
                    <div class="flex flex-wrap w-full justify-center">
                        <div
                            class="bg-dark border border-gray-500/20 rounded-md shadow-[rgb(31_45_61_/_10%)_0px_2px_10px_1px] dark:shadow-[0_2px_11px_0_rgb(6_8_24_/_39%)] p-6 text-center"
                        >
                            <div class="text-white-light bg1-white-dark w-20 h-20 rounded-full flex items-center justify-center mb-5 mx-auto">
                                <icon-box class="w-12 h-12" />
                            </div>
                            <h5 class="text-lg font-semibold mb-3.5 text-white-light">Layout Package</h5>
                            <p class="text-white-light text-[15px] mb-3.5">Lorem ipsum dolor sit amet, labore et dolore magna aliqua.</p>
                            <a href="javascript:;" class="text-info font-semibold hover:underline group">
                                Discover
                                <icon-arrow-left
                                    class="ltr:ml-1 rtl:mr-1 inline-block relative transition-all duration-300 group-hover:translate-x-2 rtl:group-hover:-translate-x-2 rtl:rotate-180"
                                />
                            </a>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code2')">
                    <highlight>
                        <pre>
&lt;!-- infobox --&gt;
&lt;div class=&quot;flex flex-wrap w-full justify-center&quot;&gt;
  &lt;div class=&quot;bg-dark border border-gray-500/20 rounded-md shadow-[rgb(31_45_61_/_10%)_0px_2px_10px_1px] dark:shadow-[0_2px_11px_0_rgb(6_8_24_/_39%)] p-6 text-center&quot;&gt;
    &lt;div class=&quot;text-white-light bg1-white-dark w-20 h-20 rounded-full flex items-center justify-center mb-5 mx-auto&quot;&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/div&gt;
    &lt;h5 class=&quot;text-lg font-semibold mb-3.5 text-white-light&quot;&gt;Layout Package&lt;/h5&gt;
    &lt;p class=&quot;text-white-light text-[15px] mb-3.5&quot;&gt;Lorem ipsum dolor sit amet, labore et dolore magna aliqua.&lt;/p&gt;
    &lt;a href=&quot;javascript:;&quot; class=&quot;text-info font-semibold hover:underline group&quot;
      &gt;Discover
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/a&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Infobox 3</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code3')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span></a
                    >
                </div>
                <div class="mb-5">
                    <div class="flex flex-wrap w-full justify-center">
                        <div
                            class="border border-gray-500/20 rounded-md shadow-[rgb(31_45_61_/_10%)_0px_2px_10px_1px] dark:shadow-[0_2px_11px_0_rgb(6_8_24_/_39%)] p-6 pt-12 mt-8 relative"
                        >
                            <div
                                class="bg-primary absolute text-white-light ltr:left-6 rtl:right-6 -top-8 w-16 h-16 rounded-md flex items-center justify-center mb-5 mx-auto"
                            >
                                <icon-box class="w-12 h-12" />
                            </div>
                            <h5 class="text-dark text-lg font-semibold mb-3.5 dark:text-white-light">Layout Package</h5>
                            <p class="text-white-dark text-[15px] mb-3.5">Lorem ipsum dolor sit amet, labore et dolore magna aliqua.</p>
                            <a href="javascript:;" class="text-primary font-semibold hover:underline group"
                                >Discover
                                <icon-arrow-left
                                    class="ltr:ml-1 rtl:mr-1 inline-block relative transition-all duration-300 group-hover:translate-x-2 rtl:group-hover:-translate-x-2 rtl:rotate-180"
                                />
                            </a>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code3')">
                    <highlight>
                        <pre>
&lt;!-- infobox --&gt;
&lt;div class=&quot;flex flex-wrap w-full justify-center&quot;&gt;
  &lt;div class=&quot;border border-gray-500/20 rounded-md shadow-[rgb(31_45_61_/_10%)_0px_2px_10px_1px] dark:shadow-[0_2px_11px_0_rgb(6_8_24_/_39%)] p-6 pt-12 mt-8 relative&quot;&gt;
    &lt;div class=&quot;bg-primary absolute text-white-light ltr:left-6 rtl:right-6 -top-8 w-16 h-16 rounded-md flex items-center justify-center mb-5 mx-auto&quot;&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/div&gt;
    &lt;h5 class=&quot;text-dark text-lg font-semibold mb-3.5 dark:text-white-light&quot;&gt;Layout Package&lt;/h5&gt;
    &lt;p class=&quot;text-white-dark text-[15px] mb-3.5&quot;&gt;Lorem ipsum dolor sit amet, labore et dolore magna aliqua.&lt;/p&gt;
    &lt;a href=&quot;javascript:;&quot; class=&quot;text-primary font-semibold hover:underline group&quot;
      &gt;Discover
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/a&gt;
  &lt;/div&gt;
&lt;/div&gt;
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
    import IconBox from '@/components/icon/icon-box.vue';
    import IconArrowLeft from '@/components/icon/icon-arrow-left.vue';

    useMeta({ title: 'Infobox' });

    const { codeArr, toggleCode } = codePreview();
</script>
