<template>
    <div>
        <ul class="flex space-x-2 rtl:space-x-reverse">
            <li>
                <a href="javascript:;" class="text-primary hover:underline">Components</a>
            </li>
            <li class="before:content-['/'] ltr:before:mr-2 rtl:before:ml-2">
                <span>Counter</span>
            </li>
        </ul>
        <div class="pt-5 space-y-8">
            <div class="panel p-3 flex items-center text-primary overflow-x-auto whitespace-nowrap">
                <div class="ring-2 ring-primary/30 rounded-full bg-primary text-white p-1.5 ltr:mr-3 rtl:ml-3">
                    <icon-bell />
                </div>
                <span class="ltr:mr-3 rtl:ml-3">Documentation: </span
                ><a href="https://www.npmjs.com/package/vue-countup-v3" target="_blank" class="block hover:underline"
                    >https://www.npmjs.com/package/vue-countup-v3</a
                >
            </div>
            <div class="grid grid-cols-1 xl:grid-cols-2 gap-6">
                <!-- Simple Counter -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Simple Counter</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code1')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <div class="mb-5 grid grid-cols-3 justify-items-center gap-3 max-w-[900px] mx-auto">
                        <div>
                            <div
                                class="w-[70px] h-[70px] sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col"
                            >
                                <count-up class="text-primary text-xl sm:text-3xl text-center" :startVal="0" :end-val="710" :duration="7"></count-up>
                            </div>
                            <h4 class="text-[#3b3f5c] text-xs sm:text-[15px] mt-4 text-center dark:text-white-dark font-semibold">HOURS</h4>
                        </div>
                        <div>
                            <div
                                class="w-[70px] h-[70px] sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col"
                            >
                                <count-up class="text-primary text-xl sm:text-3xl text-center" :startVal="0" :end-val="915" :duration="7"></count-up>
                            </div>
                            <h4 class="text-[#3b3f5c] text-xs sm:text-[15px] mt-4 text-center dark:text-white-dark font-semibold">TICKETS</h4>
                        </div>
                        <div>
                            <div
                                class="w-[70px] h-[70px] sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col"
                            >
                                <count-up class="text-primary text-xl sm:text-3xl text-center" :startVal="0" :end-val="580" :duration="7"></count-up>
                            </div>
                            <h4 class="text-[#3b3f5c] text-xs sm:text-[15px] mt-4 text-center dark:text-white-dark font-semibold">CUSTOMERS</h4>
                        </div>
                    </div>
                    <template v-if="codeArr.includes('code1')">
                        <highlight>
                            <pre>
&lt;!-- hours --&gt;
&lt;div class=&quot;mb-5 grid grid-cols-3 justify-items-center gap-3 max-w-[900px] mx-auto&quot;&gt;
  &lt;div&gt;
    &lt;div class=&quot;w-[70px] h-[70px] sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col&quot;&gt;
      &lt;count-up class=&quot;text-primary text-xl sm:text-3xl text-center&quot; :startVal=&quot;0&quot; :end-val=&quot;710&quot; :duration=&quot;7&quot;&gt;&lt;/count-up&gt;
    &lt;/div&gt;
    &lt;h4 class=&quot;text-[#3b3f5c] text-xs sm:text-[15px] mt-4 text-center dark:text-white-dark font-semibold&quot;&gt;HOURS&lt;/h4&gt;
  &lt;/div&gt;
  &lt;div&gt;
    &lt;div class=&quot;w-[70px] h-[70px] sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col&quot;&gt;
      &lt;count-up class=&quot;text-primary text-xl sm:text-3xl text-center&quot; :startVal=&quot;0&quot; :end-val=&quot;915&quot; :duration=&quot;7&quot;&gt;&lt;/count-up&gt;
    &lt;/div&gt;
    &lt;h4 class=&quot;text-[#3b3f5c] text-xs sm:text-[15px] mt-4 text-center dark:text-white-dark font-semibold&quot;&gt;TICKETS&lt;/h4&gt;
  &lt;/div&gt;
  &lt;div&gt;
    &lt;div class=&quot;w-[70px] h-[70px] sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col&quot;&gt;
      &lt;count-up class=&quot;text-primary text-xl sm:text-3xl text-center&quot; :startVal=&quot;0&quot; :end-val=&quot;580&quot; :duration=&quot;7&quot;&gt;&lt;/count-up&gt;
    &lt;/div&gt;
    &lt;h4 class=&quot;text-[#3b3f5c] text-xs sm:text-[15px] mt-4 text-center dark:text-white-dark font-semibold&quot;&gt;CUSTOMERS&lt;/h4&gt;
  &lt;/div&gt;
&lt;/div&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
import CountUp from 'vue-countup-v3';
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>
                <!-- With Icon -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">With Icon</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code2')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <div class="mb-5 grid grid-cols-3 justify-items-center gap-3 max-w-[900px] mx-auto">
                        <div>
                            <div
                                class="w-[70px] h-[70px] sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded-full border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col"
                            >
                                <count-up class="text-primary text-xl sm:text-3xl text-center" :startVal="0" :end-val="105" :duration="7"></count-up>
                            </div>
                            <h4 class="text-[#3b3f5c] text-xs sm:text-[15px] mt-4 text-center dark:text-white-dark font-semibold">
                                <icon-users class="sm:w-6 sm:h-6 text-primary mx-auto mb-2" />
                                Clients
                            </h4>
                        </div>
                        <div>
                            <div
                                class="w-[70px] h-[70px] sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded-full border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col"
                            >
                                <count-up class="text-primary text-xl sm:text-3xl text-center" :startVal="0" :end-val="300" :duration="7"></count-up>
                            </div>
                            <h4 class="text-[#3b3f5c] text-xs sm:text-[15px] mt-4 text-center dark:text-white-dark font-semibold">
                                <icon-cloud-download class="sm:w-6 sm:h-6 text-primary mx-auto mb-2" />
                                Downloads
                            </h4>
                        </div>
                        <div>
                            <div
                                class="w-[70px] h-[70px] sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded-full border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col"
                            >
                                <count-up class="text-primary text-xl sm:text-3xl text-center" :startVal="0" :end-val="58" :duration="7"></count-up>
                            </div>
                            <h4 class="text-[#3b3f5c] text-xs sm:text-[15px] mt-4 text-center dark:text-white-dark font-semibold">
                                <icon-award class="sm:w-6 sm:h-6 text-primary mx-auto mb-2" />
                                Awards
                            </h4>
                        </div>
                    </div>
                    <template v-if="codeArr.includes('code2')">
                        <highlight>
                            <pre>
&lt;!-- clients --&gt;
&lt;div class=&quot;mb-5 grid grid-cols-3 justify-items-center gap-3 max-w-[900px] mx-auto&quot;&gt;
  &lt;div&gt;
    &lt;div
      class=&quot;w-[70px] h-[70px] sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded-full border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col&quot;
    &gt;
      &lt;count-up class=&quot;text-primary text-xl sm:text-3xl text-center&quot; :startVal=&quot;0&quot; :end-val=&quot;105&quot; :duration=&quot;7&quot;&gt;&lt;/count-up&gt;
    &lt;/div&gt;
    &lt;h4 class=&quot;text-[#3b3f5c] text-xs sm:text-[15px] mt-4 text-center dark:text-white-dark font-semibold&quot;&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
      Clients
    &lt;/h4&gt;
  &lt;/div&gt;
  &lt;div&gt;
    &lt;div
      class=&quot;w-[70px] h-[70px] sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded-full border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col&quot;
    &gt;
      &lt;count-up class=&quot;text-primary text-xl sm:text-3xl text-center&quot; :startVal=&quot;0&quot; :end-val=&quot;300&quot; :duration=&quot;7&quot;&gt;&lt;/count-up&gt;
    &lt;/div&gt;
    &lt;h4 class=&quot;text-[#3b3f5c] text-xs sm:text-[15px] mt-4 text-center dark:text-white-dark font-semibold&quot;&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
      Downloads
    &lt;/h4&gt;
  &lt;/div&gt;
  &lt;div&gt;
    &lt;div
      class=&quot;w-[70px] h-[70px] sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded-full border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col&quot;
    &gt;
      &lt;count-up class=&quot;text-primary text-xl sm:text-3xl text-center&quot; :startVal=&quot;0&quot; :end-val=&quot;58&quot; :duration=&quot;7&quot;&gt;&lt;/count-up&gt;
    &lt;/div&gt;
    &lt;h4 class=&quot;text-[#3b3f5c] text-xs sm:text-[15px] mt-4 text-center dark:text-white-dark font-semibold&quot;&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
      Awards
    &lt;/h4&gt;
  &lt;/div&gt;
&lt;/div&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
import CountUp from 'vue-countup-v3';
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>
            </div>
        </div>
    </div>
</template>
<script lang="ts" setup>
    import highlight from '@/components/plugins/highlight.vue';
    import codePreview from '@/composables/codePreview';
    import CountUp from 'vue-countup-v3';
    import { useMeta } from '@/composables/use-meta';

    import IconBell from '@/components/icon/icon-bell.vue';
    import IconCode from '@/components/icon/icon-code.vue';
    import IconUsers from '@/components/icon/icon-users.vue';
    import IconCloudDownload from '@/components/icon/icon-cloud-download.vue';
    import IconAward from '@/components/icon/icon-award.vue';

    useMeta({ title: 'Counter' });

    const { codeArr, toggleCode } = codePreview();
</script>
