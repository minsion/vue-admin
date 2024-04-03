<template>
    <div>
        <ul class="flex space-x-2 rtl:space-x-reverse">
            <li>
                <a href="javascript:;" class="text-primary hover:underline">Elements</a>
            </li>
            <li class="before:content-['/'] ltr:before:mr-2 rtl:before:ml-2">
                <span>Breadcrumbs</span>
            </li>
        </ul>
        <div class="pt-5 grid grid-cols-1 lg:grid-cols-2 gap-6">
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Default</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code1')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span></a
                    >
                </div>
                <div class="mb-5">
                    <ol class="flex text-gray-500 font-semibold dark:text-white-dark">
                        <li>
                            <a href="javascript:;" class="hover:text-gray-500/70 dark:hover:text-white-dark/70">
                                <icon-home class="w-4 h-4" />
                            </a>
                        </li>
                        <li class="before:content-['/'] before:px-1.5"><a href="javascript:;">Components</a></li>
                        <li class="before:content-['/'] before:px-1.5">
                            <a href="javascript:;" class="text-black dark:text-white-light hover:text-black/70 dark:hover:text-white-light/70">UI Kit</a>
                        </li>
                    </ol>
                </div>
                <template v-if="codeArr.includes('code1')">
                    <highlight>
                        <pre>
&lt;!-- default --&gt;
&lt;ol class=&quot;flex text-gray-500 font-semibold dark:text-white-dark&quot;&gt;
  &lt;li&gt;
    &lt;a href=&quot;javascript:;&quot; class=&quot;hover:text-gray-500/70 dark:hover:text-white-dark/70&quot;&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/a&gt;
  &lt;/li&gt;
  &lt;li class=&quot;before:content-['/'] before:px-1.5&quot;&gt;&lt;a href=&quot;javascript:;&quot;&gt;Components&lt;/a&gt;&lt;/li&gt;
  &lt;li class=&quot;before:content-['/'] before:px-1.5&quot;&gt;&lt;a href=&quot;javascript:;&quot; class=&quot;text-black dark:text-white-light hover:text-black/70 dark:hover:text-white-light/70&quot;&gt;UI Kit&lt;/a&gt;&lt;/li&gt;
&lt;/ol&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Basic</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code2')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span></a
                    >
                </div>
                <div class="mb-5">
                    <ol class="flex text-gray-500 font-semibold dark:text-white-dark">
                        <li><a href="javascript:;">Components</a></li>
                        <li class="before:content-['/'] before:px-1.5">
                            <a href="javascript:;" class="text-black dark:text-white-light hover:text-black/70 dark:hover:text-white-light/70">UI Kit</a>
                        </li>
                    </ol>
                </div>
                <template v-if="codeArr.includes('code2')">
                    <highlight>
                        <pre>
&lt;!-- basic --&gt;
&lt;ol class=&quot;flex text-gray-500 font-semibold dark:text-white-dark&quot;&gt;
  &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Components&lt;/a&gt;&lt;/li&gt;
  &lt;li class=&quot;before:content-['/'] before:px-1.5&quot;&gt;&lt;a href=&quot;javascript:;&quot; class=&quot;text-black dark:text-white-light hover:text-black/70 dark:hover:text-white-light/70&quot;&gt;UI Kit&lt;/a&gt;&lt;/li&gt;
&lt;/ol&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Arrowed</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code3')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span></a
                    >
                </div>
                <div class="mb-5">
                    <ol class="flex text-primary font-semibold dark:text-white-dark">
                        <li class="bg-[#ebedf2] ltr:rounded-l-md rtl:rounded-r-md dark:bg-[#1b2e4b]">
                            <a
                                href="javascript:;"
                                class="p-1.5 ltr:pl-3 rtl:pr-3 ltr:pr-2 rtl:pl-2 relative h-full flex items-center before:absolute ltr:before:-right-[15px] rtl:before:-left-[15px] rtl:before:rotate-180 before:inset-y-0 before:m-auto before:w-0 before:h-0 before:border-[16px] before:border-l-[15px] before:border-r-0 before:border-t-transparent before:border-b-transparent before:border-l-[#ebedf2] before:z-[1] dark:before:border-l-[#1b2e4b] hover:text-primary/70 dark:hover:text-white-dark/70"
                                >Home</a
                            >
                        </li>
                        <li class="bg-[#ebedf2] dark:bg-[#1b2e4b]">
                            <a
                                class="bg-primary text-white-light p-1.5 ltr:pl-6 rtl:pr-6 ltr:pr-2 rtl:pl-2 relative h-full flex items-center before:absolute ltr:before:-right-[15px] rtl:before:-left-[15px] rtl:before:rotate-180 before:inset-y-0 before:m-auto before:w-0 before:h-0 before:border-[16px] before:border-l-[15px] before:border-r-0 before:border-t-transparent before:border-b-transparent before:border-l-primary before:z-[1]"
                                >Components</a
                            >
                        </li>
                        <li class="bg-[#ebedf2] dark:bg-[#1b2e4b]">
                            <a
                                href="javascript:;"
                                class="p-1.5 px-3 ltr:pl-6 rtl:pr-6 relative h-full flex items-center before:absolute ltr:before:-right-[15px] rtl:before:-left-[15px] rtl:before:rotate-180 before:inset-y-0 before:m-auto before:w-0 before:h-0 before:border-[16px] before:border-l-[15px] before:border-r-0 before:border-t-transparent before:border-b-transparent before:border-l-[#ebedf2] before:z-[1] dark:before:border-l-[#1b2e4b] hover:text-primary/70 dark:hover:text-white-dark/70"
                                >UI Kit</a
                            >
                        </li>
                    </ol>
                </div>
                <template v-if="codeArr.includes('code3')">
                    <highlight>
                        <pre>
&lt;!-- arrowed --&gt;
&lt;ol class=&quot;flex text-primary font-semibold dark:text-white-dark&quot;&gt;
  &lt;li class=&quot;bg-[#ebedf2] ltr:rounded-l-md rtl:rounded-r-md dark:bg-[#1b2e4b]&quot;&gt;
    &lt;a
      href=&quot;javascript:;&quot;
      class=&quot;
        p-1.5
        ltr:pl-3
        rtl:pr-3
        ltr:pr-2
        rtl:pl-2
        relative
        h-full
        flex
        items-center
        before:absolute
        ltr:before:-right-[15px]
        rtl:before:-left-[15px] rtl:before:rotate-180
        before:inset-y-0
        before:m-auto
        before:w-0
        before:h-0
        before:border-[16px]
        before:border-l-[15px]
        before:border-r-0
        before:border-t-transparent
        before:border-b-transparent
        before:border-l-[#ebedf2]
        before:z-[1]
        dark:before:border-l-[#1b2e4b]
        hover:text-primary/70
        dark:hover:text-white-dark/70
      &quot;
      &gt;Home&lt;/a
    &gt;
  &lt;/li&gt;
  &lt;li class=&quot;bg-[#ebedf2] dark:bg-[#1b2e4b]&quot;&gt;
    &lt;a
      class=&quot;
        bg-primary
        text-white-light
        p-1.5
        ltr:pl-6
        rtl:pr-6
        ltr:pr-2
        rtl:pl-2
        relative
        h-full
        flex
        items-center
        before:absolute
        ltr:before:-right-[15px]
        rtl:before:-left-[15px] rtl:before:rotate-180
        before:inset-y-0
        before:m-auto
        before:w-0
        before:h-0
        before:border-[16px]
        before:border-l-[15px]
        before:border-r-0
        before:border-t-transparent
        before:border-b-transparent
        before:border-l-primary
        before:z-[1]
      &quot;
      &gt;Components&lt;/a
    &gt;
  &lt;/li&gt;
  &lt;li class=&quot;bg-[#ebedf2] dark:bg-[#1b2e4b]&quot;&gt;
    &lt;a
      href=&quot;javascript:;&quot;
      class=&quot;
        p-1.5
        px-3
        ltr:pl-6
        rtl:pr-6
        relative
        h-full
        flex
        items-center
        before:absolute
        ltr:before:-right-[15px]
        rtl:before:-left-[15px] rtl:before:rotate-180
        before:inset-y-0
        before:m-auto
        before:w-0
        before:h-0
        before:border-[16px]
        before:border-l-[15px]
        before:border-r-0
        before:border-t-transparent
        before:border-b-transparent
        before:border-l-[#ebedf2]
        before:z-[1]
        dark:before:border-l-[#1b2e4b]
        hover:text-primary/70
        dark:hover:text-white-dark/70
      &quot;
      &gt;UI Kit&lt;/a
    &gt;
  &lt;/li&gt;
&lt;/ol&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Dotted Seperators</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code4')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span></a
                    >
                </div>
                <div class="mb-5">
                    <ol class="flex text-gray-500 font-semibold dark:text-white-dark">
                        <li><a href="javascript:;" class="hover:text-gray-500/70 dark:hover:text-white-dark/70">Home</a></li>
                        <li class="before:w-1 before:h-1 before:rounded-full before:bg-primary before:inline-block before:relative before:-top-0.5 before:mx-4">
                            <a href="javascript:;" class="text-primary">Components</a>
                        </li>
                        <li class="before:w-1 before:h-1 before:rounded-full before:bg-primary before:inline-block before:relative before:-top-0.5 before:mx-4">
                            <a href="javascript:;" class="hover:text-gray-500/70 dark:hover:text-white-dark/70">UI Kit</a>
                        </li>
                    </ol>
                </div>
                <template v-if="codeArr.includes('code4')">
                    <highlight>
                        <pre>
&lt;!-- dotted seperators --&gt;
&lt;ol class=&quot;flex text-gray-500 font-semibold dark:text-white-dark&quot;&gt;
  &lt;li&gt;&lt;a href=&quot;javascript:;&quot; class=&quot;hover:text-gray-500/70 dark:hover:text-white-dark/70&quot;&gt;Home&lt;/a&gt;&lt;/li&gt;
  &lt;li class=&quot;before:w-1 before:h-1 before:rounded-full before:bg-primary before:inline-block before:relative before:-top-0.5 before:mx-4&quot;&gt;
    &lt;a href=&quot;javascript:;&quot; class=&quot;text-primary&quot;&gt;Components&lt;/a&gt;
  &lt;/li&gt;
  &lt;li class=&quot;before:w-1 before:h-1 before:rounded-full before:bg-primary before:inline-block before:relative before:-top-0.5 before:mx-4&quot;&gt;
    &lt;a href=&quot;javascript:;&quot; class=&quot;hover:text-gray-500/70 dark:hover:text-white-dark/70&quot;&gt;UI Kit&lt;/a&gt;
  &lt;/li&gt;
&lt;/ol&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">With Icons</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code5')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span></a
                    >
                </div>
                <div class="mb-5">
                    <ol class="flex items-center flex-wrap text-gray-500 font-semibold dark:text-white-dark gap-y-4">
                        <li>
                            <a
                                href="javascript:;"
                                class="p-2.5 border border-gray-500/20 rounded-md shadow flex items-center justify-center dark:border-0 dark:bg-[#191e3a] hover:text-gray-500/70 dark:hover:text-white-dark/70"
                            >
                                <icon-home />
                            </a>
                        </li>
                        <li
                            class="flex items-center before:w-1 before:h-1 before:rounded-full before:bg-primary before:inline-block before:relative before:-top-0.5 before:mx-4"
                        >
                            <a
                                href="javascript:;"
                                class="p-2.5 border border-gray-500/20 rounded-md shadow flex items-center justify-center text-primary dark:border-0 dark:bg-[#191e3a]"
                            >
                                <icon-box class="ltr:mr-2 rtl:ml-2 shrink-0" />

                                Components
                            </a>
                        </li>
                        <li
                            class="flex items-center before:w-1 before:h-1 before:rounded-full before:bg-primary before:inline-block before:relative before:-top-0.5 before:mx-4"
                        >
                            <a
                                class="p-2.5 border border-gray-500/20 rounded-md shadow flex items-center justify-center dark:border-0 dark:bg-[#191e3a] hover:text-gray-500/70 dark:hover:text-white-dark/70"
                                href="javascript:;"
                            >
                                <icon-cpu-bolt class="ltr:mr-2 rtl:ml-2" />

                                UI Kit
                            </a>
                        </li>
                    </ol>
                </div>
                <template v-if="codeArr.includes('code5')">
                    <highlight>
                        <pre>
&lt;!-- with icons --&gt;
&lt;ol class=&quot;flex items-center flex-wrap text-gray-500 font-semibold dark:text-white-dark gap-y-4&quot;&gt;
  &lt;li&gt;
    &lt;a
      href=&quot;javascript:;&quot;
      class=&quot;p-2.5 border border-gray-500/20 rounded-md shadow flex items-center justify-center dark:border-0 dark:bg-[#191e3a] hover:text-gray-500/70 dark:hover:text-white-dark/70&quot;
    &gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/a&gt;
  &lt;/li&gt;
  &lt;li class=&quot;flex items-center before:w-1 before:h-1 before:rounded-full before:bg-primary before:inline-block before:relative before:-top-0.5 before:mx-4&quot;&gt;
    &lt;a href=&quot;javascript:;&quot; class=&quot;p-2.5 border border-gray-500/20 rounded-md shadow flex items-center justify-center text-primary dark:border-0 dark:bg-[#191e3a]&quot;&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
      Components
    &lt;/a&gt;
  &lt;/li&gt;
  &lt;li class=&quot;flex items-center before:w-1 before:h-1 before:rounded-full before:bg-primary before:inline-block before:relative before:-top-0.5 before:mx-4&quot;&gt;
    &lt;a
      class=&quot;p-2.5 border border-gray-500/20 rounded-md shadow flex items-center justify-center dark:border-0 dark:bg-[#191e3a] hover:text-gray-500/70 dark:hover:text-white-dark/70&quot;
      href=&quot;javascript:;&quot;
    &gt;
      &lt;svg&gt; ... &lt;/svg&gt;
      UI Kit
    &lt;/a&gt;
  &lt;/li&gt;
&lt;/ol&gt;
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
    import IconHome from '@/components/icon/icon-home.vue';
    import IconBox from '@/components/icon/icon-box.vue';
    import IconCpuBolt from '@/components/icon/icon-cpu-bolt.vue';

    useMeta({ title: 'Breadcrumbs' });

    const { codeArr, toggleCode } = codePreview();
</script>
